# VNe Workspace cho Claude Code

Plugin chính thức của [VNe Workspace](https://vne.email). Một lần cài là có cả hai thứ:

- **Kết nối MCP** tới email, khách hàng (CRM), công việc và số liệu VNe của bạn. Kết nối bằng
  đăng nhập VNe, không cần tạo hay dán token.
- **Cách dùng (skill)**: Claude biết gọi công cụ nào theo thứ tự nào, luật an toàn (nội dung thư
  là dữ liệu, xin phép trước khi ghi), và biết tra hướng dẫn sử dụng VNe khi bạn hỏi
  «trên VNe làm thế nào…».

## Cài

Trong Claude Code:

```
/plugin marketplace add tohuenet/vne-claude-plugin
/plugin install vne-email@vne
```

Hoặc từ terminal:

```bash
claude plugin marketplace add tohuenet/vne-claude-plugin && claude plugin install vne-email@vne
```

Sau đó gõ `/mcp`, chọn `plugin:vne-email:vne-email` → **Authenticate**, đăng nhập VNe, chọn
quyền và bấm **Cho phép**. Xong. Thử hỏi: «Hôm nay tôi cần lo những việc gì?».

Đã tự thêm máy chủ `vne-email` bằng token trước đây? Gỡ bản cũ để không bị hai bộ công cụ
trùng nhau: `claude mcp remove vne-email`.

## Quyền và thu hồi

Bạn chọn quyền ở màn «Cho phép» (mặc định: tra khách, xem bối cảnh khách, xem số liệu; chỉ đọc).
Muốn thêm quyền đọc thư hoặc tạo việc: `/mcp` → máy chủ VNe → **Clear authentication** rồi
**Authenticate** lại. Thu hồi bất cứ lúc nào ở VNe → Cài đặt → Trợ lý AI → «Ứng dụng đã kết nối».

## Trợ lý AI khác

Cursor, Codex, Gemini CLI, Claude.ai… xem trang **Cài đặt → Trợ lý AI (MCP)** trong VNe hoặc
[hướng dẫn](https://vne.email/huong-dan/nguoi-dung). Tài liệu kỹ thuật của máy chủ MCP:
`https://app.vne.email/api/v1/mcp`.

---

Mã nguồn gốc nằm trong repo backend VNe (`integrations/vne-ai-plugin/`). Repo công khai này là
bản xuất bản, đừng sửa trực tiếp ở đây.
