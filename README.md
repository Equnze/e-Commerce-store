# UG Store

Next.js (App Router) + TypeScript + Tailwind CSS v4, Better Auth, Drizzle ORM and Neon Postgres.

## Setup

1. `npm install`
2. `cp .env.example .env.local` and fill in `DATABASE_URL` (Neon) and `BETTER_AUTH_SECRET`.
3. `npm run auth:generate`: writes the Better Auth tables into `src/db/schema.ts`.
4. `npm run db:push` (or `db:generate` + `db:migrate`) to apply the schema to Neon.
5. `npm run dev`

## Layout

- `src/db/index.ts`: Drizzle client over the Neon serverless HTTP driver
- `src/db/schema.ts`: Drizzle schema (currently empty)
- `src/lib/auth.ts`: Better Auth server instance (Drizzle adapter, `pg`)
- `src/lib/auth-client.ts`: Better Auth React client
- `src/app/api/auth/[...all]/route.ts`: Better Auth route handler
- `drizzle.config.ts`: drizzle-kit config (reads `.env.local`, then `.env`)

## Scripts

`dev`, `build`, `start`, `lint`, `typecheck`, `db:generate`, `db:migrate`, `db:push`, `db:studio`, `auth:generate`
