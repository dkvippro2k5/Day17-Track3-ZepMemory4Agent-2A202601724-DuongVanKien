# Lab 17 Golden Set Report

- Implementation: `student`
- Kind: `golden`
- Cases: **20**
- Passed: **20/20**
- Evidence hit rate: **100.0%**
- Average retrieval latency: **1207.3 ms**
- Average token reduction vs full source context: **7.9%**
- Golden bonus: **10/10** (100% required)

| Case | Layer | Pass | Latency ms | Retrieved tokens | Token reduction | Missing / Error |
| --- | --- | --- | ---: | ---: | ---: | --- |
| G01 | short_term | PASS | 0.3 | 227 | 0.0% |  |
| G02 | short_term | PASS | 0.1 | 133 | 0.0% |  |
| G06 | long_term | PASS | 1508.6 | 644 | 0.0% |  |
| G09 | semantic | PASS | 339.6 | 418 | 8.9% |  |
| G10 | semantic | PASS | 251.8 | 270 | 41.2% |  |
| G14 | mixed | PASS | 2030.8 | 581 | 0.0% |  |
| G03 | long_term | PASS | 1415.7 | 898 | 0.0% |  |
| G04 | long_term | PASS | 1192.7 | 897 | 0.0% |  |
| G07 | episodic | PASS | 315.5 | 144 | 34.8% |  |
| G08 | episodic | PASS | 1220.1 | 177 | 19.9% |  |
| G11 | mixed | PASS | 1569.8 | 581 | 0.0% |  |
| G13 | mixed | PASS | 870.3 | 428 | 24.2% |  |
| G15 | mixed | PASS | 2190.1 | 762 | 0.0% |  |
| G16 | mixed | PASS | 1381.5 | 581 | 0.0% |  |
| G17 | mixed | PASS | 2608.7 | 581 | 0.0% |  |
| G18 | mixed | PASS | 1238.1 | 489 | 13.5% |  |
| G19 | mixed | PASS | 1371.6 | 537 | 5.0% |  |
| G05 | long_term | PASS | 1149.9 | 897 | 0.0% |  |
| G12 | mixed | PASS | 1828.6 | 560 | 11.4% |  |
| G20 | mixed | PASS | 1661.4 | 756 | 0.0% |  |

## Evidence excerpts

### G01 - short_term

`<SESSION_SUMMARY> user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. | assistant: Noted standup constraint. | user: Constraint HOLD-BETA-STAGING: writes go to staging DB only. | assistant: Noted staging constraint. | user: Filler A about button padding. | assistant: Filler A. | user: Filler B about color tokens. | assistant: Filler B. | user: Filler C about copy tone. | assistant: Filler C. </SESSION_SUMMARY> <DURABLE_NOTES> - user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. - assistant: Noted standup constraint. - user: Constraint HOLD-BETA-STAGING: writes go to staging DB only. - assistant: Noted staging constraint. </DURA`

### G02 - short_term

`<RECENT_TURNS> user: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. assistant: Da hieu: demo ca nhan ORCHID-27, uu tien Python, tranh Java, vi du ngan. user: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. assistant: Toi se uu tien timeline khi giai thich coroutine va Task. user: TODO: hoan thanh benchmark report truoc thu Sau luc 16:00. Day la open loop LAB-REPORT-1600. </RECENT_TURNS>`

### G06 - long_term

`<USER_SUMMARY> The user's project is LOTUS-88, and they prioritize Java and Spring Boot for backend development, explicitly not using Python. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-01 11:00:00     Source: message     Content: [user] {   "user_id": "lan-lab17",   "first_name": "Lan",   "last_name": "Tran",   "user_alias": "Lan Tran" }: Toi la Lan. Du an cua toi la LOTUS-88. Toi uu tien Java va Spring Boot, va khong dung Python trong vi du backend.   - Created At: 2026-08-01 11:00:20     Source: message     Content: Lab Assistant (assistant): Da hieu: LOTUS-88, Java + Spring Boot cho backend examples.   - C`

### G09 - semantic

`EPISODE: For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transient 5xx errors, use exponential-backoff, and stop after max-3-retries. Marker: PAYMENT-RULE-3. metadata= EPISODE: Reserve bounded context for memory. This lab uses short-term 10 percent, long-term 4 percent, episodic 3 percent, semantic 3 percent; trim lower-priority memory first. Marker: BUDGET-10-4-3-3. metadata= EPISODE: {"id":"kb-payment-retry","entity":"Payment API Retry Policy","summary":"For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transient 5xx errors, use exponential-backoff, and stop after max-3-retries. Mark`

### G10 - semantic

`EPISODE: Reserve bounded context for memory. This lab uses short-term 10 percent, long-term 4 percent, episodic 3 percent, semantic 3 percent; trim lower-priority memory first. Marker: BUDGET-10-4-3-3. metadata= EPISODE: {"id":"kb-memory-privacy","entity":"Agent Memory Privacy Rule","summary":"Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marker: DELETE-VERIFY-ALL.","source":"memory-governance-policy","updated_at":"2026-08-12T00:00:00Z"} metadata= EPISODE: Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marke`

### G14 - mixed

`<LONG_TERM> <USER_SUMMARY> The user's project is LOTUS-88, and they prioritize Java and Spring Boot for backend development, explicitly not using Python. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-17 09:37:46     Source: message     Content: [user] {   "user_id": "lan-lab17",   "first_name": "Lan",   "last_name": "Tran",   "user_alias": "Evaluation User" }: Lan uu tien stack backend nao cho LOTUS-88?   - Created At: 2026-08-01 11:00:20     Source: message     Content: Lab Assistant (assistant): Da hieu: LOTUS-88, Java + Spring Boot cho backend examples.   - Created At: 2026-08-01 11:00:00     Source: message `

### G03 - long_term

`<USER_SUMMARY> The user's personal project is named ORCHID-27, for which they prefer Python. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this project. The user previously completed a benchmark report that was an open loop LAB-REPORT-1600, due by Friday at 16:00. The user debugged async HTTP issues, finding that connection churn was the main problem, not the timeout threshold. Reusing the aiohttp ClientSession and setting concurrency to 20 was an effective solution.  The user prefers Python and dislikes Java. They want brief examples when code is explained. For personal demos like ORCHID-27, Python is preferred, but for th`

### G04 - long_term

`<USER_SUMMARY> The user's personal project is named ORCHID-27, for which they prefer Python. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this project. The user previously completed a benchmark report that was an open loop LAB-REPORT-1600, due by Friday at 16:00. The user debugged async HTTP issues, finding that connection churn was the main problem, not the timeout threshold. Reusing the aiohttp ClientSession and setting concurrency to 20 was an effective solution.  The user prefers Python and dislikes Java. They want brief examples when code is explained. For personal demos like ORCHID-27, Python is preferred, but for th`

### G07 - episodic

`EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. EPISODE: Da ghi nhan trajectory: increase timeout khong hieu qua; ClientSession + concurrency=20 giai quyet connection churn. EPISODE: Voi demo ca nhan cua Minh, ngon ngu uu tien la gi? EPISODE: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. EPISODE: Hom nay toi debug async HTTP. Toi da thu tang timeout len 60s nhung van fail.`

### G08 - episodic

`EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. EPISODE: Da tach scope: BLUEBIRD-42 dung TypeScript/NestJS; ORCHID-27 van uu tien Python. EPISODE: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. EPISODE: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. EPISODE: Cuoi tuan minh ngoi mot minh lam demo rieng, khong hop team. Truoc khi chon template, nhac lai: khi lam viec ca nhan minh uu tien ngon ngu nao, va ma du an demo ca nhan la gi?`

### G11 - mixed

`<LONG_TERM> <USER_SUMMARY> The user's personal project is named ORCHID-27, for which they prefer Python. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this project. The user previously completed a benchmark report that was an open loop LAB-REPORT-1600, due by Friday at 16:00. The user debugged async HTTP issues, finding that connection churn was the main problem, not the timeout threshold. Reusing the aiohttp ClientSession and setting concurrency to 20 was an effective solution.  The user prefers Python and dislikes Java. They want brief examples when code is explained. For personal demos like ORCHID-27, Python is preferred`

### G13 - mixed

`<EPISODIC> EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. EPISODE: Hom nay toi debug async HTTP. Toi da thu tang timeout len 60s nhung van fail. EPISODE: Hay chon huong dan code retry payment phu hop voi preference ca nhan cua Minh. EPISODE: Cuoi tuan minh ngoi mot minh lam demo rieng, khong hop team. Truoc khi chon template, nhac lai: khi lam viec ca nhan minh uu tien ngon ngu nao, va ma du an demo ca nhan la gi? Chi  EPISODE: Mai hop mentor, toi nay minh muon don open-loop. Liet ke viec chua dong, deadline, va ma dinh danh task. Can du ba manh de ghi vao note hop. <`

### G15 - mixed

`<LONG_TERM> <USER_SUMMARY> The user's personal project is named ORCHID-27, for which they prefer Python. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this project. The user previously completed a benchmark report that was an open loop LAB-REPORT-1600, due by Friday at 16:00. The user debugged async HTTP issues, finding that connection churn was the main problem, not the timeout threshold. Reusing the aiohttp ClientSession and setting concurrency to 20 was an effective solution.  The user prefers Python and dislikes Java. They want brief examples when code is explained. For personal demos like ORCHID-27, Python is preferred`

### G16 - mixed

`<LONG_TERM> <USER_SUMMARY> The user's personal project is named ORCHID-27, for which they prefer Python. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this project. The user previously completed a benchmark report that was an open loop LAB-REPORT-1600, due by Friday at 16:00. The user debugged async HTTP issues, finding that connection churn was the main problem, not the timeout threshold. Reusing the aiohttp ClientSession and setting concurrency to 20 was an effective solution.  The user prefers Python and dislikes Java. They want brief examples when code is explained. For personal demos like ORCHID-27, Python is preferred`

### G17 - mixed

`<LONG_TERM> <USER_SUMMARY> The user's personal project is named ORCHID-27, for which they prefer Python. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this project. The user previously completed a benchmark report that was an open loop LAB-REPORT-1600, due by Friday at 16:00. The user debugged async HTTP issues, finding that connection churn was the main problem, not the timeout threshold. Reusing the aiohttp ClientSession and setting concurrency to 20 was an effective solution.  The user prefers Python and dislikes Java. They want brief examples when code is explained. For personal demos like ORCHID-27, Python is preferred`

### G18 - mixed

`<EPISODIC> EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. EPISODE: Cuoi tuan minh ngoi mot minh lam demo rieng, khong hop team. Truoc khi chon template, nhac lai: khi lam viec ca nhan minh uu tien ngon ngu nao, va ma du an demo ca nhan la gi? Chi  EPISODE: Minh sap viet script ca nhan de tai hien su co latency, muon code dung ngon ngu minh thich khi lam mot minh, dong thoi bam sat playbook incident cua lab chu dung vo tang timeout. G EPISODE: Toi nay minh viet tool ca nhan de tai hien su co HTTP roi sua dung playbook. Can ba manh: ngon ngu minh thich khi lam mot minh,`

### G19 - mixed

`<LONG_TERM> <USER_SUMMARY> The user's personal project is named ORCHID-27, for which they prefer Python. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this project. The user previously completed a benchmark report that was an open loop LAB-REPORT-1600, due by Friday at 16:00. The user debugged async HTTP issues, finding that connection churn was the main problem, not the timeout threshold. Reusing the aiohttp ClientSession and setting concurrency to 20 was an effective solution.  The user prefers Python and dislikes Java. They want brief examples when code is explained. For personal demos like ORCHID-27, Python is preferred`

### G05 - long_term

`<USER_SUMMARY> The user's personal project is named ORCHID-27, for which they prefer Python. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this project. The user previously completed a benchmark report that was an open loop LAB-REPORT-1600, due by Friday at 16:00. The user debugged async HTTP issues, finding that connection churn was the main problem, not the timeout threshold. Reusing the aiohttp ClientSession and setting concurrency to 20 was an effective solution.  The user prefers Python and dislikes Java. They want brief examples when code is explained. For personal demos like ORCHID-27, Python is preferred, but for th`

### G12 - mixed

`<LONG_TERM> <USER_SUMMARY> The user's personal project is named ORCHID-27, for which they prefer Python. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this project. The user previously completed a benchmark report that was an open loop LAB-REPORT-1600, due by Friday at 16:00. The user debugged async HTTP issues, finding that connection churn was the main problem, not the timeout threshold. Reusing the aiohttp ClientSession and setting concurrency to 20 was an effective solution.  The user prefers Python and dislikes Java. They want brief examples when code is explained. For personal demos like ORCHID-27, Python is preferred`

### G20 - mixed

`<SHORT_TERM> <SESSION_SUMMARY> user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. | assistant: Noted standup constraint. | user: Filler about dashboard widgets. | assistant: Filler. | user: Filler about CSS variables. | assistant: Filler. | user: Filler about copy review. | assistant: Filler. </SESSION_SUMMARY> <DURABLE_NOTES> - user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. - assistant: Noted standup constraint. </DURABLE_NOTES> <RECENT_TURNS> user: Filler about empty charts. assistant: Filler. user: Filler about telemetry. assistant: Filler. user: Filler about a11y labels. assistant: Filler. </RECENT_TURNS> </SHORT_TERM>`
