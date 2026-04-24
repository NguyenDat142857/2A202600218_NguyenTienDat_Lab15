2A202600218_NguyenTienDat_Lab15
AICB-P1 · Ngày 15 — Phiếu bài tập 0–5 (Buổi sáng)
Kịch bản 3: Trợ lý Tuyển sinh & Hỗ trợ Sinh viên
Tên nhóm: Nhóm C16
Ngày: 2026-04-22
________________________________________
08:00–08:15 | Khởi động & Điểm lại nhanh
Ý kiến cá nhân (tổng hợp nhóm):
1.	Nhóm đã nắm vững pipeline RAG cơ bản và kỹ thuật tạo prompt nhờ từng xây dựng chatbot FAQ.
2.	Còn yếu trong việc ước lượng chi phí vận hành và thiết kế hệ thống chịu tải lớn.
3.	Chưa có kinh nghiệm xử lý lưu lượng đột biến trong mùa tuyển sinh.
4.	Mong muốn tìm hiểu sâu về triển khai thực tế, tối ưu chi phí và độ tin cậy.
5.	Cần hiểu rõ hơn các quy định về bảo vệ dữ liệu cá nhân (Nghị định 13/2023).
________________________________________
08:15–08:40 | Phiếu 0 — Lộ trình Học tập
1. Ba kỹ năng nhóm tự tin nhất
#	Kỹ năng	Mô tả ngắn
1	Thiết kế RAG pipeline	Kết hợp truy xuất tài liệu với LLM để trả lời chính xác các câu hỏi tuyển sinh
2	Prompt engineering & hệ thống prompt	Viết chỉ dẫn rõ ràng, kiểm soát phong cách và vai trò của AI agent
3	Tích hợp API & sử dụng công cụ	Gọi API để tra cứu điểm, nộp hồ sơ, kiểm tra lịch thi qua function calling
2. Mô tả sản phẩm/kịch bản
Trợ lý AI tư vấn tuyển sinh và hỗ trợ tân sinh viên, triển khai trên nền tảng web. Sử dụng RAG trên kho FAQ tuyển sinh, quy chế đào tạo và các biểu mẫu. Có khả năng tra cứu hồ sơ cá nhân có kiểm soát và chuyển tiếp sang cán bộ khi cần. Ngôn ngữ chính là tiếng Việt (có dấu, không dấu và teencode). Hỗ trợ tiếng Anh sẽ phát triển khi có đủ sinh viên quốc tế.
Ba nhóm người dùng:
•	Thí sinh & phụ huynh: quan tâm đến điểm chuẩn, ngành học, học phí, hạn nộp hồ sơ.
•	Sinh viên năm nhất: đăng ký môn học, ký túc xá, lịch nhập học.
•	Cán bộ tuyển sinh: theo dõi các câu hỏi phổ biến qua dashboard, duyệt câu trả lời nhạy cảm.
3. Chủ đề xuyên suốt cả ngày
"Làm thế nào để triển khai AI tuyển sinh đủ tin cậy, đủ tiết kiệm và đủ nhanh trong mùa cao điểm?"
4. Trả lời ba câu hỏi bắt buộc
Câu hỏi	Trả lời
Sản phẩm giải quyết bài toán gì?	Giảm tải cho tổng đài trong mùa tuyển sinh, cung cấp thông tin nhất quán 24/7, cập nhật nhanh theo từng đợt xét tuyển.
Ai là người dùng chính?	Thí sinh & phụ huynh (hàng chục nghìn người trong mùa cao điểm), sinh viên năm nhất, cán bộ tuyển sinh.
Vì sao phù hợp để phân tích triển khai & chi phí?	Lưu lượng biến động mạnh theo mùa → bài toán mở rộng. Dữ liệu hai tầng (công khai + PII) → cần cân nhắc cloud hay hybrid. Chi phí LLM tỷ lệ với số request → dễ tăng đột biến. Độ chính xác là yếu tố sống còn → bắt buộc có sự tham gia của con người.
________________________________________
08:40–09:25 | Phiếu 1 — Phân tích Triển khai Doanh nghiệp
1. Bối cảnh tổ chức
•	Trường đại học công/tư, quy mô khoảng 10.000 sinh viên.
•	Phòng CNTT nội bộ nhỏ (5-10 người), ngân sách IT ở mức trung bình.
•	Hệ thống hiện có: cổng thông tin sinh viên (SIS), CRM tuyển sinh, website WordPress, email/tổng đài.
•	Các phòng ban liên quan: Tuyển sinh (nội dung), Đào tạo (quy chế), CNTT (hạ tầng).
2. Dữ liệu hệ thống can thiệp
Loại dữ liệu	Ví dụ	Nơi lưu trữ
Công khai — FAQ & quy định	Điểm chuẩn, học phí, chỉ tiêu, quy chế, biểu mẫu	Website, CMS
Nội bộ — Hồ sơ ứng viên	Họ tên, CCCD, điểm thi, nguyện vọng	CRM tuyển sinh (on prem)
Nội bộ — Học tập sinh viên	Kết quả học tập, đăng ký môn học	SIS (on prem)
Nhật ký hội thoại	Lịch sử chat, câu hỏi thường gặp	Hệ thống AI (cloud)
3. Đánh giá độ nhạy cảm dữ liệu: TRUNG BÌNH
Yếu tố	Đánh giá
Loại PII	Họ tên, CCCD, điểm thi, nguyện vọng — nhạy cảm nhưng không thuộc nhóm y tế/tài chính
Quy định áp dụng	Nghị định 13/2023/NĐ CP về bảo vệ dữ liệu cá nhân
Rủi ro nếu lộ	Ảnh hưởng uy tín trường, bị phạt hành chính, có thể bị kiện
Audit trail	CÓ — ai truy vấn hồ sơ nào, lúc nào, từ IP nào
4. Ba ràng buộc doanh nghiệp lớn nhất
#	Ràng buộc	Tác động nếu không xử lý
1	Lưu lượng tăng 10 20 lần vào mùa tuyển sinh (30 50 lần ngay khi công bố điểm)	Hệ thống quá tải → thí sinh không tra cứu được → khiếu nại, mất uy tín
2	Nội dung thay đổi theo từng đợt (điểm chuẩn, chỉ tiêu, quy chế cập nhật 3 5 lần/năm)	AI trả lời thông tin cũ → sai lệch → ảnh hưởng đến quyết định của thí sinh
3	Phản hồi phải nhanh và chính xác — sai deadline/thủ tục sẽ gây hậu quả	Thí sinh thường đối chiếu điểm chuẩn trên web chính thức nhưng các thủ tục rườm rà lại dễ bị hướng dẫn sai
5. Mô hình triển khai chọn: HYBRID (Cloud + On prem)
6. Hai lý do chính
Lý do 1 – Chi phí theo mùa: Lưu lượng cao chỉ xảy ra vài tuần mỗi năm. Nếu mua sắm on prem để đáp ứng đỉnh điểm, phần lớn thời gian còn lại sẽ lãng phí. Cloud với cơ chế tự động mở rộng giúp chỉ trả tiền khi dùng, phù hợp với khối lượng công việc biến động.
Lý do 2 – Tuân thủ quy định: Hồ sơ thí sinh (CCCD, điểm, nguyện vọng) đã có sẵn trong CRM/SIS nội bộ. Giữ nguyên vị trí đó và chỉ cho phép truy xuất qua Lookup API có kiểm soát (trả về các trường được phép, không lộ dữ liệu thô) → giảm rủi ro theo Nghị định 13/2023.
Kiến trúc hai tầng
Tầng	Thành phần	Ghi chú
Cloud (biến động)	API Gateway + Load Balancer, LLM inference (Claude API), Vector DB cho FAQ công khai (Qdrant), Semantic cache (Redis), Monitoring (Grafana/Datadog)	Tự động mở rộng theo nhu cầu
On prem (hiện có)	CRM tuyển sinh, SIS (kết quả học tập), Audit log, Lookup API nội bộ	Không thay đổi, tận dụng hạ tầng sẵn có
Lưu ý: Lookup API nội bộ (kết nối cloud ↔ on prem) cần đội CNTT xây dựng và bảo trì — phải tính vào chi phí vận hành.
Gợi ý thảo luận
Câu hỏi	Trả lời
Cần audit trail không?	CÓ — ghi nhận ai hỏi gì về hồ sơ, lúc nào, từ đâu
Dữ liệu có được đưa ra khỏi tổ chức không?	FAQ công khai: CÓ ; Hồ sơ thí sinh: KHÔNG
Cần tích hợp hệ thống cũ không?	CÓ — CRM tuyển sinh, SIS, cổng thông tin sinh viên
Trả lời sai thì ai bị ảnh hưởng đầu tiên?	Thí sinh (mất cơ hội nhập học) → Nhà trường (uy tín, kiện tụng)
________________________________________
09:35–10:15 | Phiếu 2 — Phân tích Chi phí
1. Ước lượng lưu lượng
Chỉ số	Ngoài cao điểm (~46 tuần)	Cao điểm (~6 tuần)
User/ngày	~1.000	~8.000–10.000
Request/ngày	~3.000	~30.000–40.000
Lượt hội thoại/session (TB)	2 3	3 5
Concurrent cao nhất	~10	~100 200
2. Ước lượng token mỗi request
Phần	Số token
System prompt	~400 (đã được viết gọn)
Ngữ cảnh RAG (top 3 đoạn × 300 token)	~900
Câu hỏi của user	~100
Tổng đầu vào	~1.400
Đầu ra	~300
Không tính lịch sử nhiều lượt vào baseline vì phần lớn câu hỏi mùa tuyển sinh chỉ đơn lẻ.
3. Các lớp chi phí (MVP/năm)
Nhóm	Hạng mục	USD/năm
Kỹ thuật	LLM API tokens	$2.500–3.500
	Embedding + Vector DB	$700–1.200
	Compute (API server, tự động mở rộng)	$1.000–1.800
	Lưu trữ + Logging + Monitoring	$700–1.200 + $700–1.300
	Tạm tính kỹ thuật	~$4.900–7.700
Vận hành	Xem xét thủ công (human review)	$1.500–3.000
	Bảo trì (cập nhật nội dung/prompt, reindex, đánh giá)	$3.500–5.500
	Xây dựng & bảo trì Lookup API	$1.500–3.000
	Tạm tính vận hành	~$6.500–11.500
TỔNG/NĂM		~$11.400–19.200
4. Chi phí sơ bộ ở mức MVP
Trung bình khoảng $950–1.600/tháng (~25 40 triệu VNĐ/tháng). Con số này hợp lý nếu so với mức lương của 2 3 cán bộ tuyển sinh toàn thời gian.
5. Khi mở rộng 5x/10x — phần nào tăng mạnh nhất?
Kịch bản	Chi phí token	Compute	Lưu trữ	Xem xét thủ công
5x users	+500%	+200%	+50%	+300%
10x users	+1000%	+400%	+100%	+500%
→ Chi phí token/API tăng tuyến tính, trở thành yếu tố chi phí số 1 khi mở rộng.
→ Chi phí xem xét thủ công cũng tăng nhanh nếu độ chính xác chưa cao.
Câu hỏi bắt buộc
Câu hỏi	Trả lời
Yếu tố chi phí lớn nhất?	Token LLM vào mùa cao điểm (~55 60% chi phí inference tập trung trong 6 tuần)
Chi phí ẩn dễ quên?	Reindex embedding mỗi đợt (3 5 lần/năm), xem xét thủ công các câu nhạy cảm, môi trường staging/testing (+15 20% hạ tầng), bảo trì rule based fallback theo đợt
Chỗ nào ước lượng quá lạc quan?	Số lượt hội thoại/session có thể cao hơn (thí sinh lo lắng có thể hỏi 8 15 lượt thay vì 3). Nhiều nhóm quên tính chi phí cho cán bộ QA.
So sánh với thị trường
Benchmark	Nguồn tham khảo	So sánh
Chatbot FAQ đại học (Mỹ, ~15k SV)	Case study Drift/Intercom edu sector	$18k–25k/năm (cao hơn ước tính của nhóm)
Chatbot tuyển sinh ĐH FPT (VN, ước tính)	Báo cáo công khai + tin tuyển dụng	~$15k–20k/năm (gần với nhóm)
Kết luận		Ước tính của nhóm nằm trong dải hợp lý, đã bao gồm phần xem xét thủ công và bảo trì Lookup API.
________________________________________
10:15–10:50 | Phiếu 3 — Tranh luận Tối ưu Chi phí
Chiến lược 1: Semantic Caching — ✅ LÀM NGAY (MVP v1.0)
Mục	Nội dung
Tiết kiệm	Chi phí token và độ trễ — cắt 40 60% số lần gọi LLM trong cao điểm (hit rate ~50 70% cho FAQ lặp lại). Ngoài cao điểm thấp hơn (~20 30%)
Lợi ích	Giảm chi phí token · Độ trễ ~200ms từ cache thay vì 2 3s từ LLM · Giảm tải cho nhà cung cấp · Tăng thông lượng
Đánh đổi	Cache bị cũ khi nội dung vừa cập nhật → cần cơ chế vô hiệu hóa theo đợt · Cần điều chỉnh ngưỡng tương đồng
Thời điểm	Ngay từ MVP v1.0 — câu hỏi tuyển sinh lặp lại rất nhiều
Công cụ/stack	Redis + embedding similarity cosine ≥ 0.92, TTL theo đợt
Ví dụ: “điểm chuẩn ngành CNTT năm nay?” và “ngành CNTT lấy bao nhiêu điểm?” → một lần gọi LLM phục vụ mọi biến thể.
Chiến lược 2: Định tuyến Model / Phân tầng — ✅ LÀM NGAY (MVP v1.1)
Mục	Nội dung
Tiết kiệm	~30 40% chi phí token (so với baseline dùng toàn bộ Sonnet)
Lợi ích	Giảm mạnh chi phí · Độ trễ đường nhanh giảm · Model lớn không bị lãng phí cho câu hỏi đơn giản
Đánh đổi	Cần xây classifier/router · Rủi ro route sai (câu phức tạp gặp model yếu) → cần đánh giá liên tục
Thời điểm	MVP v1.1 — sau khi có đủ log để hiệu chỉnh router
Định tuyến 3 tầng:
Tầng	Loại câu hỏi (tỉ lệ)	Xử lý	Chi phí
🟢 Tier 1 — FAQ đơn giản	60 70%	Vector search top 1 → template response, không cần LLM	~$0
🟡 Tier 2 — Tư vấn thông thường	25 30%	Claude Haiku 3.5 + RAG	$0.8/1M input
🔴 Tier 3 — Câu nhạy cảm/phức tạp	5 10%	Claude Sonnet 4.6 + Xem xét thủ công	$3/1M input + nhân sự
Chiến lược 3: Nén Prompt + Tối ưu Ngữ cảnh RAG — ⏳ Phase 2
Mục	Nội dung
Tiết kiệm	20 30% token đầu vào
Lợi ích	Giảm chi phí mà không ảnh hưởng chất lượng nếu làm đúng · Giảm độ trễ
Đánh đổi	Prompt quá ngắn có thể giảm độ chính xác. Giảm số đoạn truy xuất có thể thiếu ngữ cảnh. Cần A/B test kỹ
Thời điểm	System prompt gọn: MVP. Tinh chỉnh RAG (giảm 5→3 đoạn + thêm reranker): Phase 2 — cần dữ liệu đánh giá trước
Ngưỡng bắt đầu Nén Prompt: cần ít nhất 500 request production có nhãn chất lượng (thích/không thích hoặc đánh giá thủ công) để A/B test đảm bảo độ chính xác không bị ảnh hưởng.
Chiến lược 4: Prompt Caching (phía API của Anthropic) — ✅ LÀM NGAY (MVP v1.0)
Mục	Nội dung
Tiết kiệm	Giảm ~90% chi phí token đầu vào cho phần system prompt + ngữ cảnh RAG được cache
Lợi ích	System prompt (~400 token) lặp lại mỗi request → cache hit từ lượt thứ 2 trở đi. Đặc biệt hiệu quả trong session nhiều lượt. Chi phí đọc cache = 10% so với đầu vào đầy đủ
Đánh đổi	Cache TTL 5 phút → phù hợp với session chat liên tục; cần thiết kế cấu trúc prompt sao cho phần ổn định đứng đầu, phần động (câu hỏi user) đứng sau
Thời điểm	MVP v1.0 — bật ngay khi tích hợp Claude API, chi phí thực hiện gần như bằng 0
Công cụ/stack	Anthropic cache_control: {"type": "ephemeral"} trên system prompt và các khối RAG tĩnh
Low hanging fruit: với ~1.400 token đầu vào mỗi request và 40.000 request/ngày vào cao điểm, caching system prompt 400 token tiết kiệm ~$4 6/ngày peak — không lớn nhưng tốn gần như không công sức.
Chiến lược 5: Batch API cho Tác vụ Bất đồng bộ — ⏳ Phase 2
Mục	Nội dung
Tiết kiệm	50% chi phí so với sync API (theo định giá Batch API của Anthropic)
Lợi ích	Phù hợp với tác vụ không cần real time: kiểm tra trạng thái hồ sơ phức tạp, tổng hợp câu hỏi phổ biến cuối ngày, tạo sẵn câu trả lời cho top 200 FAQ trước ngày công bố
Đánh đổi	Kết quả trả sau tối đa 24h → chỉ dùng cho use case bất đồng bộ, không thay thế đường sync
Thời điểm	Phase 2 — sau khi phân loại rõ request nào có thể xử lý bất đồng bộ
Chốt ưu tiên
Chiến lược	Tiết kiệm ước tính	Làm ngay?
Semantic Caching	40 60% số lần gọi LLM peak	✅ MVP v1.0
Anthropic Prompt Caching	~90% chi phí phần system prompt	✅ MVP v1.0
Model Routing	~30 40% chi phí token	✅ MVP v1.1
Prompt Compression	20 30% token đầu vào	⏳ Phase 2
Batch API	50% chi phí cho request bất đồng bộ	⏳ Phase 2
Kết hợp các chiến lược → ước tính giảm 55 65% tổng chi phí LLM so với baseline không tối ưu.
10:50–11:25 | Phiếu 4 — Bàn về Mở rộng & Độ tin cậy
Tình huống 1: Lưu lượng tăng đột biến
Bối cảnh: Ngày công bố điểm chuẩn, lưu lượng tăng từ 3.000 → 40.000+ request/ngày trong vài giờ.
Khía cạnh	Chi tiết
Tác động đến user	Chat lag/timeout, thí sinh thử lại → tăng tải thêm, tổng đài quá tải
Phản ứng ngắn hạn	Giới hạn tốc độ theo IP · Trả cache/static ngay + thông báo "câu trả lời chi tiết sẽ có trong 2 phút" · Banner dẫn link bảng điểm chuẩn tĩnh
Giải pháp dài hạn	K8s HPA tự động mở rộng · Pre warm cache cho top 200 câu hỏi trước ngày công bố · Load test (k6/Locust) trước mỗi mùa
Tình huống 2: LLM Provider timeout/ngừng hoạt động
Bối cảnh: Claude API trả về timeout 100% trong 15 phút giữa mùa cao điểm.
Khía cạnh	Chi tiết
Tác động đến user	Bot không trả lời hoặc báo lỗi → mất niềm tin
Phản ứng ngắn hạn	Circuit breaker sau 5 timeout → chuyển sang 1 provider fallback duy nhất (Claude → GPT 4o mini). Retry exponential backoff: 2 lần (1s, 2s) rồi kích hoạt fallback
Giải pháp dài hạn	Rule based intent matcher cho top 50 FAQ + chế độ degraded mode có thông báo rõ (“Đang hoạt động ở chế độ hạn chế”). Không thiết lập 3 provider vì bảo trì prompt cho nhiều provider = chi phí ẩn lớn
Tình huống 3: Phản hồi chậm >5s
Bối cảnh: P95 latency tăng từ 2s lên 8s do RAG retrieval chậm hoặc LLM quá tải.
Khía cạnh	Chi tiết
Tác động đến user	Thí sinh nghĩ bot bị đơ, refresh liên tục → vòng lặp xấu
Phản ứng ngắn hạn	Streaming SSE (user thấy chữ xuất hiện trong ~500ms) · Hard timeout 5s → trả link FAQ tĩnh
Giải pháp dài hạn	Vector DB read replica vào mùa peak · Reranker nhỏ hơn · Precompute embedding cho tài liệu nóng
Phân loại request
Loại	Ví dụ	Xử lý
Real time cần	FAQ lookup, kiểm tra deadline, thông tin học phí	Sync, streaming
Async có thể	Kiểm tra trạng thái hồ sơ phức tạp, câu cần tra cứu DB sinh viên	Queue, trả kết quả sau
Các chỉ số cần giám sát
Chỉ số	SLO Target	Ngưỡng cảnh báo
p95 latency — FAQ được cache	< 500ms	> 800ms
p95 latency — FAQ + Haiku	< 2s	> 3s
p95 latency — Tư vấn Sonnet	< 5s	> 7s
Tỷ lệ lỗi LLM API	< 0.5%	> 1%
Tỷ lệ hit cache (cao điểm)	> 50%	< 30%
Tỷ lệ chuyển tiếp cho con người	< 10%	> 20%
Tỷ lệ lỗi im lặng (silent failure)	< 1%	> 2%
Phát hiện lỗi im lặng: LLM trả lời sai nội dung mà không có lỗi HTTP là điểm yếu cố hữu của chatbot. Cách phát hiện:
1.	Điểm tin cậy: Nếu RAG retrieval score < 0,75 → gắn cờ “low confidence” → log + tăng ưu tiên xem xét thủ công.
2.	Kiểm tra nhất quán: Với top 50 câu FAQ quan trọng (điểm chuẩn, học phí, deadline) → chạy đánh giá tự động hàng ngày so với ground truth.
3.	Tín hiệu từ user: Tỉ lệ user hỏi lại cùng intent trong cùng session > 2 lần → nghi ngờ câu trả lời sai.
4.	Guardrail từ khóa: Dùng regex giám sát đầu ra cho các số điểm chuẩn, học phí, ngày tháng — nếu lệch khỏi khoảng hợp lý → tự động giữ lại + chuyển sang Tier 3.
Đề xuất Fallback (5 tầng)
 
11:25–11:45 | Phiếu 5 — Bản đồ Kỹ năng & Hướng đi
📄 Bảng 1 — Tự đánh giá năng lực (copy vào Word)
STT	Thành viên	Business/Product	Infra/Data/Ops	AI Engineering/Application
1	Nguyễn Tiến Đạt	3	4	4
2	Phạm Đan Kha	4	3	4
3	Ngô Văn Long	3	5	4
4	Nguyễn Duy Hiếu	4	4	5
5	Lê Minh Quân	2	5	3
6	Trần Gia Huy	3	4	5
	Trung bình nhóm	3.2	4.2	4.2
________________________________________
📄 Bảng 2 — Đánh giá tổng quan
STT	Nội dung	Chi tiết
1	Mạnh nhất	AI Engineering/Application và Infra/Data/Ops (~4.2/5)
2	Yếu nhất	Business/Product (~3.2/5)
3	Nhận xét tổng quan	       Nhóm có nền tảng kỹ thuật tốt, đặc biệt trong việc xây dựng hệ thống AI, xử lý dữ liệu và triển khai prototype nhanh. Tuy nhiên, kỹ năng về tư duy sản phẩm, phân tích nhu cầu người dùng và định hướng kinh doanh còn hạn chế.
      Một số thành viên có xu hướng tập trung vào kỹ thuật mà chưa chú trọng đến bức tranh tổng thể của sản phẩm.
3. Hướng đi Phase 2: AI Application Track
Lý do phù hợp với Kịch bản 3:
•	Chưa có prototype → việc xây dựng trước, mở rộng sau là ưu tiên số 1 (Application > Productization).
•	Điểm Infra/Ops (4.3/5) ngang với AI Engineer/Application (4.3/5) → Application Track tận dụng thế mạnh, tránh rủi ro từ Productization Track vốn yêu cầu Kubernetes/CI/CD thành thục.
•	Kịch bản thiên về trải nghiệm người dùng, cần mở rộng đa kênh: web (kênh chính của thí sinh & phụ huynh Việt Nam).
•	Cần pipeline đánh giá đặc thù cho lĩnh vực tuyển sinh (độ chính xác là yếu tố sống còn) — đây là vấn đề thuộc tầng Application.
Tại sao không chọn Productization Track dù Infra/Ops = 4.3?
Productization yêu cầu hệ thống đang chạy production cần monitoring/CD/hardening độ tin cậy. Nhóm hiện chưa có hệ thống để productize. Sẽ xem xét lại sau khi prototype hoàn thiện (Phase 3).
Sản phẩm bàn giao Phase 2:
1.	Prototype RAG chatbot kèm đánh giá RAGAS (faithfulness, answer relevancy)
2.	Bộ chuyển đổi đa kênh (web)
3.	Dashboard dành cho cán bộ tuyển sinh (xem câu hỏi hàng đầu, duyệt câu nhạy cảm)
4.	Bộ test gồm 200 câu hỏi cho lĩnh vực tuyển sinh
4. 2–3 kỹ năng cần bổ sung
#	Kỹ năng cần bổ sung	Mảng	Cách học
1	Framework đánh giá RAG (Ragas, TRULENS) — Đo lường các chỉ số faithfulness (tính trung thực), answer relevancy (mức độ liên quan của câu trả lời) và context precision (độ chính xác của ngữ cảnh truy xuất).	AI Engineering / Application	Khóa "Building and Evaluating Advanced RAG" trên DeepLearning.Ai; Thực hành với thư viện RAGAS trên bộ dữ liệu tuyển sinh.
2	LLM Observability (Langfuse, Arize Phoenix) — Theo dõi toàn bộ vòng đời của một request: từ trace đầu vào/đầu ra, giám sát chi phí theo từng user/session, phát hiện câu trả lời sai qua phân tích độ tin cậy, và thiết lập dashboard cảnh báo.	Infra / Ops	Đọc tài liệu chính thức của Langfuse (đặc biệt phần self-host trên Docker); Xây dựng POC tracing cho prototype RAG.
3	Tuân thủ Nghị định 13/2023 về bảo vệ dữ liệu cá nhân — Hiểu rõ các điều khoản về dữ liệu nhạy cảm (Điều 9), yêu cầu về nhật ký xử lý (Điều 21-23) và giới hạn chuyển dữ liệu ra nước ngoài (Điều 26) để thiết kế kiến trúc hybrid và luồng xin phê duyệt phù hợp.	Business / Product	Đọc và phân tích Nghị định 13/2023/NĐ-CP; Tham khảo các case study triển khai chatbot trong ngành giáo dục tại Việt Nam.

