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
