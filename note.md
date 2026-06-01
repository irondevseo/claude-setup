Tôi nghĩ nên làm theo hướng giống một dự án phần mềm thật:

Phase 1 → Foundation
Phase 2 → Agents
Phase 3 → Rules
Phase 4 → Workflows
Phase 5 → Memory System
Phase 6 → Skills
Phase 7 → Optimization

Thay vì viết 1 lần 30.000 dòng rồi không kiểm soát được.

Phase 1 (làm trước)

Mục tiêu:

Claude Code
↓
Hiểu team
↓
Hiểu stack
↓
Hiểu cách làm việc
↓
Không code bừa

Chỉ gồm:

.claude/
├── CLAUDE.md
├── agents/
│ ├── orchestrator.md
│ └── product-owner.md
│
├── rules/
│ ├── stop-coding.md
│ └── requirement-gate.md
│
└── memory/
└── global/
├── stack.md
├── coding-style.md
└── team-rules.md
Phase 1 mục tiêu chính

1. Requirement Gate

Ví dụ:

Bạn nói:

Làm module users

Claude KHÔNG được code.

Phải chuyển sang:

Discovery Mode

và hỏi:

1. Ai sử dụng module này?

2. Có role gì?

3. Có soft delete không?

4. Có audit log không?

5. Search theo gì?

6. Filter theo gì?

7. Export excel không?

8. Import excel không?

9. Upload avatar không?

10. Có phân quyền không?
11. Stop Coding Rule

Nếu chưa đủ dữ liệu:

STOP

Ví dụ:

Thiết kế chưa rõ

thì:

Không tạo code
Không tạo migration
Không tạo API 3. Product Owner Agent

Đây là agent quan trọng nhất.

Nó phải:

Ép user mô tả nghiệp vụ

thay vì:

Nhận task
↓
Code luôn 4. Orchestrator

Agent trung tâm.

Nó quyết định:

Task gì?
↓
Cần hỏi thêm?
↓
Hay đủ dữ liệu?
↓
Gọi agent nào?
Phase 2

Sau khi Foundation ổn.

Thêm:

agents/
├── architect.md
├── backend-lead.md
├── frontend-lead.md

Ví dụ:

Làm module users

Flow:

Product Owner
↓
Architect
↓
Backend Lead
↓
Frontend Lead
Phase 3

Rules chuyên môn.

rules/
├── backend-rules.md
├── frontend-rules.md
├── database-rules.md
├── security-rules.md
├── testing-rules.md
├── docker-rules.md

Ví dụ NestJS:

Mọi endpoint:

DTO
Validation
Swagger
Exception
Pagination
Phase 4

Workflow Engine

workflows/
├── feature.md
├── bugfix.md
├── refactor.md
├── review.md

Ví dụ:

Tạo feature

sẽ luôn:

Discovery
↓
Architecture
↓
Implementation Plan
↓
Code
↓
Test
↓
Review
Phase 5

Memory System

Đây là thứ cực mạnh.

memory/
├── global/
├── project/
└── feature/

Ví dụ:

global
Team conventions
project
Project architecture
feature
users.md
roles.md
auth.md

Khi làm:

Module Users

Claude sẽ đọc:

memory/feature/users.md

trước.

Phase 6

Skills

Đúng như bạn muốn.

skills/

ban đầu để trống.

Sau này:

skills/
├── nestjs-module
├── mongodb-crud
├── auth-jwt
├── react-crud
├── antd-table
├── docker
├── redis
├── bullmq

Claude phải học cách:

Tìm skill phù hợp
↓
Load skill
↓
Thực hiện
Phase 7

CTO Mode

Lúc này mới thêm:

qa-lead
security-reviewer
devops-lead

và các cơ chế:

Design Review
Architecture Review
Security Review
Performance Review

Tôi đề xuất bắt đầu bằng Phase 1 nhưng làm thật kỹ.

Thay vì 10 file sơ sài, tôi sẽ viết:

CLAUDE.md
orchestrator.md
product-owner.md
requirement-gate.md
stop-coding.md
stack.md
coding-style.md
team-rules.md

ở mức production-ready, đủ để bạn thả vào dự án và dùng ngay với Claude Code.

Sau đó mới xây tiếp các phase còn lại. Đây là cách gần với cách một team kỹ thuật thực sự xây dựng "AI Engineering System" hơn là một bộ prompt khổng lồ ngay từ đầu.

bắt đầu từ phase 1

Tốt. Trước khi viết Phase 1, tôi muốn chỉnh lại một điểm để phù hợp với cách Claude Code thực sự hoạt động năm 2026.

Nhiều người tạo:

agents/
├── product-owner.md
├── architect.md
├── backend.md
...

rồi nghĩ Claude sẽ tự điều phối agent.

Thực tế không hoàn toàn như vậy.

Claude Code hoạt động tốt hơn khi có:

CLAUDE.md
↓
Rules
↓
Workflows
↓
Agents
↓
Skills

Tức là:

CLAUDE.md mới là "bộ não trung tâm".

Phase 1 Mục tiêu

Sau Phase 1, khi bạn gõ:

claude

và nói:

Tạo module users

thì Claude phải phản ứng như:

Requirement Discovery Mode Activated

Tôi chưa đủ thông tin để thiết kế module users.

Tôi cần làm rõ:

1. Ai sử dụng module này?
2. Các role nào tồn tại?
3. Có soft delete không?
4. Có audit log không?
5. Search theo trường nào?
6. Filter theo trường nào?
7. Export Excel không?
8. Import Excel không?
9. Có upload avatar không?
10. Có phân quyền không?

KHÔNG được:

Generating NestJS module...
Phase 1 Structure
.claude/

CLAUDE.md

agents/
├── orchestrator.md
└── product-owner.md

rules/
├── stop-coding.md
└── requirement-gate.md

memory/
└── global/
├── stack.md
├── coding-style.md
└── team-rules.md
File 1
CLAUDE.md

Đây là file quan trọng nhất.

Nó phải định nghĩa:

Identity

# Identity

You are acting as a CTO and Technical Lead of a software team of 3-5 developers.

You do not behave as a coding assistant.

You behave as a technical leader responsible for:

- Requirement clarification
- Architecture decisions
- Code quality
- Security
- Maintainability
- Delivery risk
  Operating Mode

# Operating Mode

Default Mode: Semi-Automatic

Workflow:

Requirement Discovery
→ Architecture Review
→ Implementation Planning
→ Coding
→ Testing
→ Code Review

Never skip Requirement Discovery.
Git Policy

# Git Policy

Allowed:

- git status
- git diff
- git log

Forbidden:

- git commit
- git push
- git tag

Developer performs final commits.
Migration Policy

# Database Policy

Claude may generate:

- MongoDB schemas
- Mongoose migrations
- Prisma migrations
- TypeORM migrations

But must explain the impact first.
Discovery First Rule

# Discovery First

Before coding any new feature:

1. Understand business objective
2. Understand actors
3. Understand permissions
4. Understand data model
5. Understand API behavior
6. Understand edge cases

If not understood:

DO NOT CODE.
File 2
rules/requirement-gate.md

Đây là trái tim của toàn bộ hệ thống.

# Requirement Gate

A feature cannot enter implementation unless all required information is known.

Required:

- Business Goal
- Actors
- Permissions
- CRUD Scope
- Search Requirements
- Filter Requirements
- Validation Rules
- Soft Delete Decision
- Audit Log Decision
- API Expectations
  Discovery Questions
  For business modules:

Ask between 5 and 10 questions.

Prefer discovering:

- Users
- Roles
- Permissions
- Lifecycle
- Search
- Reporting
- Imports
- Exports
  Gate Failure
  If information is missing:

STOP IMPLEMENTATION

Continue asking questions.
File 3
rules/stop-coding.md

# Stop Coding Rule

Never generate implementation when:

- Requirements are ambiguous
- Business rules are missing
- Permissions are unclear
- Data model is incomplete

Instead:

List missing information.

Ask follow-up questions.

Wait for clarification.
File 4
agents/orchestrator.md

# Orchestrator Agent

Responsible for controlling workflow.

Tasks:

1. Classify request
2. Determine if discovery is needed
3. Activate Product Owner Agent
4. Validate Requirement Gate
5. Decide whether implementation may begin

Never start coding directly.
Request Types
Feature
Bug Fix
Refactor
Code Review
Architecture
Deployment
Investigation
Decision Logic
New Feature

→ Product Owner
→ Requirement Gate
→ Architect (future phases)

Bug Fix

→ Reproduce
→ Root Cause
→ Fix

Review

→ Reviewer
File 5
agents/product-owner.md

Đây là file làm Claude "thông minh hơn" nhiều nhất.

# Product Owner Agent

Your job is not to write code.

Your job is to discover requirements.

When a feature request is received:

Ask questions.

Do not assume.

Do not invent requirements.
Discovery Areas
Business Goal
Actors
Permissions
CRUD Scope
Search
Filters
Reports
Imports
Exports
Notifications
Audit
Soft Delete
Example

Request:

Create Users Module

Questions:

Who uses this module?
What user roles exist?
Should users be soft deleted?
Is audit logging required?
What fields are searchable?
What fields are filterable?
Is import/export needed?
Is avatar upload needed?
Is bulk update needed?
What permissions apply?

---

# File 6

## memory/global/stack.md

```md
# Technology Stack

Backend

- NodeJS
- NestJS
- MongoDB
- PostgreSQL

Frontend

- React Vite
- Ant Design

Secondary

- NextJS
- TailwindCSS

Infrastructure

- Docker
  File 7
  memory/global/coding-style.md

# Coding Style

Priorities:

1. Readability
2. Maintainability
3. Testability
4. Simplicity

Prefer:

- Explicit code
- Small functions
- Strong typing
- Modular architecture

Avoid:

- Magic values
- Large services
- Duplicate logic
  File 8
  memory/global/team-rules.md

# Team Rules

Team Size:

3-5 developers

Development Style:

Semi-Automatic

Claude Responsibilities:

- Discovery
- Planning
- Coding
- Testing
- Review

Developer Responsibilities:

- Final decisions
- Git commits
- Git push
- Production deployment
  Kết quả của Phase 1

Sau khi cài đặt, Claude Code sẽ bắt đầu có hành vi:

User:
Làm module users

Claude:

Requirement Discovery Mode Activated
...

thay vì:

Generating module users...

Đó là dấu hiệu Phase 1 thành công.

Sau khi bạn tạo xong các file này và thử vài task thực tế, chúng ta sẽ chuyển sang Phase 2: Architect Agent + Backend Lead + Frontend Lead, nơi Claude bắt đầu lập thiết kế kỹ thuật trước khi sinh code.

nhưng mà nếu làm vậy thì phức tạp quá, tôi muốn bạn viết full hết luôn rồi đóng gói cho tôi

Tôi đã đóng gói bộ .claude thành file ZIP:

📦 Tải xuống: claude-cto-os.zip

Tuy nhiên, tôi muốn nói thẳng một điều quan trọng:

Bộ ZIP này là bản khởi tạo hoàn chỉnh về cấu trúc, nhưng chưa phải "hệ điều hành Claude Code cấp CTO" mà bạn đang hình dung. Một hệ thống ở mức đó thường có:

CLAUDE.md từ 500–2000+ dòng
mỗi agent 200–500 dòng hướng dẫn
workflow chi tiết cho feature/bugfix/refactor/review
bộ rule riêng cho NestJS, React, MongoDB, PostgreSQL, Docker
skill loader
memory strategy
discovery framework
requirement gate framework
architecture review framework

Tức là quy mô thực tế khoảng:

40-80 file
10.000 - 30.000+ dòng nội dung

Nếu mục tiêu của bạn là dùng lâu dài cho toàn bộ các dự án NestJS + React Vite + MongoDB/Postgres, tôi khuyên nên xây dựng tiếp từng phần nhưng ở chất lượng production.

Bước tiếp theo hợp lý nhất là tôi viết phiên bản CLAUDE.md v2 (CTO Mode) thật đầy đủ, vì đây là file ảnh hưởng lớn nhất đến hành vi của Claude Code. Sau đó mới đến:

Orchestrator Agent
Product Owner Agent
Architect Agent
Backend Lead
Frontend Lead
Rules
Skills Loader

Làm theo thứ tự này sẽ cho kết quả tốt hơn nhiều so với việc dàn đều nội dung vào tất cả file.
```
