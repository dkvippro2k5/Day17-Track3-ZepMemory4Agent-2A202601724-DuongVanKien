# README_submission — Lab 17 Multi-Memory Agent (Zep)

## 1. Ba câu bắt buộc

**Layer quan trọng nhất trong bộ test này:** `long_term` (Context Block). 4/11 case (E02, E03, E08, E09) phụ thuộc trực tiếp, và nó cũng là thành phần bắt buộc của case mixed E07. Không có long-term, agent không thể phân biệt sở thích Python (ORCHID-27) với ràng buộc TypeScript/NestJS (BLUEBIRD-42, E08), và không cách ly được dữ liệu Minh/Lan (E09).

**Trade-off Context Block/Zep vs tự dựng Redis+Qdrant:** Zep tự trích fact/quan hệ thành knowledge graph, tự xếp hạng liên quan và tự xử lý recency/conflict — đổi lại latency cao hơn (long_term ~2.3s vs Redis gần 0ms) và ta không kiểm soát chi tiết ranking. Redis+Qdrant nhanh, rẻ nhưng phải tự viết toàn bộ extract-fact, conflict-resolution, user isolation.

**Guardrail chống memory poisoning:** heartbeat/background job không được tự cấp quyền hoặc tự ghi instruction mới vào durable memory (`AGENTS.md`); mọi durable write phải giữ source/timestamp/confidence để audit/rollback; `consent.json` chặn ingest nếu user chưa opt-in.

## 2. Bốn câu phân tích benchmark

1. **Layer hit rate thấp nhất:** cả 4 layer đạt 100% (11/11). Nếu xét rủi ro, `long_term` mong manh nhất: 4/5 case của nó có token reduction = 0% (sát trần budget 4%) — dễ FAIL nhất nếu profile user phình to hơn.
2. **Query nhiều token nhất:** E03 (899 tok) và E02 (898 tok), cả hai long_term — Context Block trả cả user summary thay vì lọc riêng theo câu hỏi.
3. **E07 (mixed) cần kết hợp:** `long_term` (preference Python) + `semantic` (`Idempotency-Key`). Thiếu 1 trong 2 evidence là FAIL.
4. **Token reduction vs hit rate:** memory-enabled reduction 20.2% / hit rate 100%; no-memory reduction 81.8% / hit rate 18.2%. No-memory "giảm token" vô nghĩa vì không retrieve gì — reduction chỉ có giá trị khi đọc cùng hit rate.

## 3. E08 (recency) và E10 (compaction)

**E08:** Context Block giải quyết theo "recency + scope", không xoá fact cũ: Python (ORCHID-27) và TypeScript/NestJS (BLUEBIRD-42) tồn tại song song vì khác scope, không mâu thuẫn thật — đúng `control_plane/MEMORY.md`.

**E10:** Giảm `max_recent_messages` 6→4, `sliding` vẫn giữ `REVIEW-DEADLINE-1600` nhờ `extract_durable_notes` tách nó vào `DURABLE_NOTES` trước khi bị compact khỏi `RECENT_TURNS` — compaction ưu tiên constraint/deadline, không chỉ tóm tắt hội thoại.
