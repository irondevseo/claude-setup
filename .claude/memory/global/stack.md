# Global Technology Stack

This document tracks allowed and configured technologies in the current workspace. Ensure all developed features align with this stack.

*Note: Developers can edit this file when migrating or updating libraries.*

## Core Stack

### Backend
- **Node.js**: LTS version.
- **Framework**: NestJS (TypeScript).
- **ORM / Database Client**:
  - TypeORM or Prisma (for SQL databases).
  - Mongoose (for MongoDB).
- **Databases**:
  - PostgreSQL (Primary Relational).
  - MongoDB (Primary NoSQL).

### Frontend
- **Runtime**: React (Vite).
- **Styling**: TailwindCSS & Ant Design (Tokens & Components).
- **State Management**:
  - React Query / TanStack Query (Server State caching).
  - Zustand or React Context (Client local state).
- **Router**: React Router DOM or NextJS App Router.

## Auxiliary / Tooling Stack
- **Docker**: Containerized environment for local DBs and microservices.
- **Validation**: `class-validator`, `zod`.
- **Testing**: Jest, Vitest, Playwright.
- **Format / Lint**: Prettier, ESLint.
