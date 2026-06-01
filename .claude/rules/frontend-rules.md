# Frontend Quality Rules (React & Ant Design)

Adhere to these rules when writing frontend code.

## 1. Component Design
- Max file length for React components: **300 lines**. If it exceeds this, extract sub-components or logic into hooks.
- Keep layout separate: Do not put page structure layouts inside business inputs.
- Keep inline styles to a minimum: Prefer CSS Modules, Tailwind, or Styled Components.

## 2. API & Data Fetching
- Wrap all endpoints in service layers. Components must never import libraries like `axios` or use `fetch` directly.
- Use query clients (React Query/SWR) to handle caching, stale states, loading indicators, and mutation side effects.
- Declare request/response types strictly.

## 3. Ant Design Conventions (If stack applies)
- Wrap inputs inside `<Form.Item>` to leverage built-in validation and styling.
- Set `<Table>` rowKey prop to a unique ID (typically `record => record.id` or `record => record._id`).
- Always specify loading props on tables, buttons, and modals while async operations are running.

## 4. UI Error & State Coverage
- Empty state: Show a customized placeholder when datasets are empty.
- Error boundary: Wrap major blocks to catch component crashes.
- Toast notifications: Inform users on success/error mutation actions using `notification` or `message` components.
