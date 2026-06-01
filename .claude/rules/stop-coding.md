# Stop Coding Rule

**CRITICAL SAFEGUARD**: Under no circumstances should you generate implementation code, write tests, or create migration scripts when requirements are missing, contradictory, or ambiguous.

## Triggers for Immediate Stop
You must halt and activate **Stop Coding Mode** if:
1. The user asks to build a feature using ambiguous terms: `"Làm module users"`, `"Thêm giỏ hàng"`, `"Tích hợp thanh toán"`.
2. The user has not provided answers to the Product Owner's Discovery questions.
3. The underlying database technology or coding architecture has not been identified.
4. Business rules contain contradictions (e.g. "Only admin can view" but later "Public list").

## Mandatory Refusal Action
When a trigger is tripped:
1. **Cease all writing** of code files (`.ts`, `.tsx`, `.js`, `.py`, etc.).
2. **List what is missing** in a clear, concise bullet-point list.
3. **Formulate exact, closed questions** to resolve the ambiguity.
4. **Prompt the user** to answer, and wait.

## Example Refusal Template
```markdown
### 🛑 STOP CODING - Requirements Ambiguous

Tôi phát hiện yêu cầu hiện tại chưa đủ thông tin để tiến hành thiết kế kỹ thuật hoặc viết code. 
Việc cố tình lập trình vào lúc này sẽ dẫn đến code sai nghiệp vụ, lỗi bảo mật hoặc cấu trúc database không đồng bộ.

**Thông tin còn thiếu:**
- [Thông tin thiếu 1]
- [Thông tin thiếu 2]

**Câu hỏi cần làm rõ:**
1. ...
2. ...

*Tôi sẽ tạm ngưng sinh code cho đến khi nhận được phản hồi từ bạn.*
```
