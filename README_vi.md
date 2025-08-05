ScrapeGraphAI là gì?
ScrapeGraphAI là một thư viện Python mã nguồn mở giúp bạn tự động thu thập dữ liệu (web scraping) từ website hoặc các file dữ liệu như XML, HTML, JSON, Markdown,...
Điểm đặc biệt là ScrapeGraphAI sử dụng AI (cụ thể là các mô hình ngôn ngữ lớn - LLM) để hiểu yêu cầu của bạn và tự động xây dựng “đường dẫn” thu thập dữ liệu (gọi là scraping pipeline), bạn chỉ cần nói bạn muốn lấy thông tin gì!

Dùng ScrapeGraphAI để làm gì?
Tự động lấy dữ liệu từ bất cứ website nào hoặc file dữ liệu.

Không cần biết lập trình phức tạp hay viết từng dòng code để “bóc tách” dữ liệu.

Có thể kết nối với nhiều công cụ AI khác nhau: OpenAI, Groq, Gemini, Azure, hoặc mô hình AI cài trên máy (như Ollama).

Hỗ trợ tích hợp nhanh với các nền tảng No-code/Low-code (Zapier, Bubble, Pipedream...) nếu bạn không chuyên code.

Cách hoạt động của ScrapeGraphAI?
1. Bạn chỉ cần nhập yêu cầu
Ví dụ:

“Hãy lấy thông tin mô tả, tên người sáng lập, và các link mạng xã hội của công ty này.”

2. Chọn nguồn cần lấy
Có thể là link website, hoặc file trên máy.

3. AI sẽ tự làm việc còn lại
AI sẽ đọc nội dung trang web/file, xác định vị trí thông tin cần lấy, và xuất kết quả ra file hoặc in ra màn hình.

Cài đặt nhanh
Chỉ cần 2 dòng lệnh trong terminal:

bash
Sao chép
Chỉnh sửa
pip install scrapegraphai
playwright install   # Dùng để hỗ trợ lấy dữ liệu web
Nên cài trong môi trường ảo (virtual environment) để tránh lỗi xung đột thư viện.

Ví dụ sử dụng cơ bản
python
Sao chép
Chỉnh sửa
from scrapegraphai.graphs import SmartScraperGraph

graph_config = {
    "llm": {"model": "ollama/llama3.2", "model_tokens": 8192},
    "verbose": True,
    "headless": False,
}

smart_scraper_graph = SmartScraperGraph(
    prompt="Hãy lấy mô tả công ty, tên sáng lập, và các link mạng xã hội",
    source="https://scrapegraphai.com/",
    config=graph_config
)

result = smart_scraper_graph.run()
import json
print(json.dumps(result, indent=4))
Chú ý: Nếu bạn muốn dùng OpenAI (ChatGPT) chỉ cần đổi cấu hình model.

Kết quả sẽ ra sao?
Kết quả trả về là một dictionary chứa dữ liệu bạn cần, ví dụ:

python
Sao chép
Chỉnh sửa
{
    "description": "...",
    "founders": [...],
    "social_media_links": {...}
}
ScrapeGraphAI phù hợp với ai?
Người mới học code, hoặc không biết code cũng dùng được (kết nối qua các nền tảng không cần code).

Ai làm về data, nghiên cứu, marketing, AI,... cần lấy dữ liệu web tự động với tốc độ nhanh.

Những ai muốn xây dựng hệ thống lấy dữ liệu lớn (scrape at scale).

Thông tin thêm
Tài liệu chi tiết: Tại đây

Có API, SDK cho Python và Node.js.

Tham gia cộng đồng Discord nếu cần hỗ trợ.

Tóm lại:
Chỉ cần bạn biết mình muốn lấy gì từ website, ScrapeGraphAI sẽ tự động lấy cho bạn bằng AI, cực kỳ nhanh và tiện!


ScrapeGraphAI là thư viện mã nguồn mở, nên việc sử dụng thư viện này để viết code và chạy trên máy tính cá nhân (local) hoàn toàn miễn phí. Tuy nhiên, chi phí thực tế sẽ phụ thuộc vào mô hình AI (LLM) mà bạn sử dụng để “scrape” dữ liệu, và bạn có thể sẽ phát sinh chi phí trong các trường hợp sau:

1. Chạy Local: MIỄN PHÍ (gần như 100%)
Nếu bạn dùng model AI chạy trên máy của bạn, ví dụ như sử dụng Ollama hoặc các mô hình open-source (Llama, Mistral, Gemma, v.v...):

ScrapeGraphAI: Miễn phí (không thu phí bản quyền)

Ollama và các model open-source: Miễn phí

Chi phí duy nhất: Máy tính bạn phải đủ mạnh (CPU/RAM/Ổ cứng, hoặc có GPU càng tốt)

Không tốn phí API, không cần nạp tiền

2. Dùng API có tính phí (như OpenAI, Gemini, Azure, Groq, v.v)
Nếu bạn cấu hình ScrapeGraphAI để sử dụng API của các nhà cung cấp mô hình AI thương mại (ví dụ: ChatGPT của OpenAI):

ScrapeGraphAI: Miễn phí

Chi phí phát sinh: Trả tiền cho API theo mức tiêu thụ token/ký tự (giống như trả tiền cho ChatGPT hoặc Gemini API)

Ví dụ chi phí (tham khảo tháng 8/2025):

OpenAI GPT-4o: ~5 USD/triệu token đầu vào, ~15 USD/triệu token đầu ra.

Gemini Pro: Khoảng 0.5 - 1 USD/triệu token (cập nhật theo Google Cloud).

Groq: Mức giá riêng từng model, thường rẻ hơn OpenAI.

Cách tính chi phí:

Mỗi lần ScrapeGraphAI chạy sẽ gửi prompt + văn bản cần đọc lên server AI → bị tính token (số lượng ký tự).

Nếu bạn scrape nhiều trang web lớn, hoặc scrape nhiều lần, chi phí có thể tăng nhanh.

Nếu chỉ chạy thử hoặc lấy dữ liệu nhỏ, hầu như không tốn nhiều tiền.

3. Dùng dịch vụ SaaS ScrapeGraphAI.com
Nếu bạn đăng ký sử dụng trực tiếp trên website ScrapeGraphAI.com (không phải chạy trên máy cá nhân), họ có thể thu phí theo gói/tháng hoặc theo lượt sử dụng API.

Giá chi tiết cần tham khảo trực tiếp trên ScrapeGraphAI.com/pricing (tùy thời điểm có miễn phí thử nghiệm hoặc không).

4. Một số chi phí phụ khác (nếu có):
Hạ tầng cloud: Nếu bạn chạy trên server, có thể tốn thêm phí máy chủ, lưu trữ,...

Dịch vụ tích hợp (Zapier, Bubble...): Có thể mất phí riêng tùy theo gói nền tảng bạn sử dụng.

Tóm tắt bảng chi phí
Loại sử dụng	Phí ScrapeGraphAI	Phí AI Model	Các phí khác
Chạy local (Ollama, v.v)	Miễn phí	Miễn phí	Máy tính cá nhân
API OpenAI, Gemini,...	Miễn phí	Tính phí theo API	Không
SaaS (ScrapeGraphAI.com)	Theo gói/usage	Đã gồm trong giá	Không
Tích hợp nền tảng khác	Theo gói riêng	Theo từng platform	Có thể có

Lời khuyên cho người mới:
Nếu chỉ muốn học hoặc thử nghiệm:
➡️ Chạy local với model open-source hoàn toàn không tốn phí.

Nếu cần chất lượng cao nhất hoặc tốc độ nhanh:
➡️ Sử dụng API của OpenAI, Groq, Gemini, nhưng chú ý kiểm soát số lần gọi API để tránh phát sinh chi phí lớn.
