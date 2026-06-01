# Claude CTO OS Setup

Đây là bộ setup Agentic AI Coding Assistant toàn diện dành cho **Claude Code** (phiên bản chạy CLI, desktop hoặc vscode). Bộ setup này chuyển đổi Claude từ một trợ lý viết code thụ động thành một **CTO / Tech Lead** ảo nhằm giúp bạn quản lý dự án hiệu quả, hạn chế tối đa việc sinh code ẩu hoặc sai nghiệp vụ.

## 🚀 Tính năng nổi bật
1. **Requirement Gate**: Bắt buộc phát hiện và làm rõ nghiệp vụ (5-10 câu hỏi) trước khi viết bất kỳ dòng code nào.
2. **Stop Coding Rule**: Tự động dừng sinh code khi yêu cầu mơ hồ hoặc thiếu cấu trúc dữ liệu.
3. **Multi-Agent Simulation**: Phân luồng công việc qua các agent chuyên biệt: Orchestrator -> Product Owner -> Architect -> Backend/Frontend Lead.
4. **Trực quan hóa quy trình**: Các bước hoạt động từ Discovery -> Architecture Design -> Implementation -> Testing -> Code Review & Delivery.
5. **Memory System**: Quản lý bộ nhớ dự án qua cấu trúc thư mục phân tầng (`global/`, `project/`, `feature/`).

## 📁 Cấu trúc thư mục Setup
Khi sao chép vào dự án của bạn, hãy đảm bảo cấu trúc thư mục sau được giữ nguyên:
```
.claude/
├── CLAUDE.md                # Bộ não trung tâm (CTO Mode) điều phối hành vi của Claude
├── settings.json            # Cài đặt quyền hạn công cụ & Hooks tự động
├── agents/                  # Các nhân diện Agent chuyên biệt
│   ├── orchestrator.md      # Điều phối và phân loại task
│   ├── product-owner.md     # Khám phá nghiệp vụ (Discovery)
│   ├── architect.md         # Thiết kế kiến trúc, DB Schema & API Contract
│   ├── backend-lead.md      # Tiêu chuẩn và thực thi code phía Server
│   └── frontend-lead.md     # Tiêu chuẩn và thực thi code phía Client
├── rules/                   # Quy chuẩn chất lượng & Rào cản nghiệp vụ
│   ├── stop-coding.md       # Rào cản bắt buộc dừng sinh code khi thiếu thông tin
│   ├── requirement-gate.md  # Ma trận thông tin nghiệp vụ tối thiểu cần có
│   ├── backend-rules.md     # Quy định code NestJS/NodeJS sạch
│   ├── frontend-rules.md    # Quy định code React/Ant Design sạch
│   ├── database-rules.md    # Quy định thiết kế Schema & Migration an toàn
│   └── security-rules.md    # Quy tắc bảo mật (SQL Injection, XSS, JWT...)
├── workflows/               # Các luồng làm việc tuần tự chi tiết
│   ├── feature.md           # Quy trình phát triển tính năng mới
│   ├── bugfix.md            # Quy trình tìm lỗi, sửa đổi và kiểm thử
│   ├── refactor.md          # Quy trình tối ưu hóa code và giảm nợ kỹ thuật
│   └── review.md            # Quy trình đánh giá chất lượng trước khi bàn giao
└── memory/
    └── global/              # Bộ nhớ ngữ cảnh chung của dự án
        ├── stack.md         # Danh sách công nghệ được phép sử dụng
        ├── coding-style.md  # Phong cách viết code và đặt tên
        └── team-rules.md    # Phân chia vai trò giữa Dev và Claude
```

## 🛠️ Hướng dẫn tích hợp vào dự án mới
Để áp dụng bộ setup này vào bất kỳ dự án nào của bạn, hãy làm theo các bước sau:

1. **Copy thư mục `.claude/`**: Sao chép toàn bộ thư mục `.claude/` này và đặt ở thư mục gốc (root) của dự án mới.
2. **Copy file `CLAUDE.md`**: Đảm bảo file `CLAUDE.md` nằm ở thư mục gốc của dự án của bạn để Claude Code tự động tải nó khi khởi động.
3. **Cập nhật Stack & Style**:
   - Mở `.claude/memory/global/stack.md` và chỉnh sửa lại các công nghệ thực tế dự án đang dùng (ví dụ: Django, Spring Boot, VueJS, Postgres...).
   - Mở `.claude/memory/global/coding-style.md` để sửa lại chuẩn viết code của team bạn.

## 💻 Cách hoạt động trong thực tế
Khi bạn khởi động `claude` hoặc mở Claude Code lên và đưa ra một yêu cầu mới:

**Ví dụ yêu cầu**: *"Làm module users"*

**Hành vi của Claude sau khi có setup này**:
1. Claude kích hoạt **Requirement Discovery Mode** thông qua Product Owner Agent.
2. Claude hiển thị cảnh báo **Stop Coding** (Không tạo code, không tạo database schema lúc này).
3. Claude gửi danh sách 5-10 câu hỏi để làm rõ: *Ai dùng module này? Có phân quyền gì? Có soft delete hay audit log không? Các trường nào cần tìm kiếm?...*
4. Sau khi bạn trả lời, Claude xác nhận mở khóa cổng **Requirement Gate**, gọi Architect Agent thiết kế DB/API và gửi bạn duyệt kế hoạch.
5. Chỉ khi bạn đồng ý, Claude mới bắt đầu lập trình.
