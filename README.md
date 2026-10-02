# Academic Demo

An academic / admin dashboard web app built with **Next.js 14 (App Router)**, **Material UI 5**, **Tailwind CSS**, **Prisma (SQLite)** and **NextAuth.js**. It is based on the Vuexy MUI Next.js admin template and includes dashboards, an academy (e-learning) app, and many ready-made app modules.

## Features

- Dashboards: CRM and Analytics
- Apps: Academy, eCommerce, Email, Chat, Calendar, Kanban, Invoice, Logistics, Users, Roles & Permissions
- Authentication with NextAuth (credentials + Google OAuth) and Prisma adapter
- Multi-language support (English, French, Arabic) with RTL layout
- Light / dark mode and a theme customizer
- Forms, form wizards and validation (React Hook Form + Valibot)
- Data tables (TanStack Table) and charts (ApexCharts, Recharts)
- Front pages: landing page, pricing, help center, checkout

## Tech Stack

| Area | Tools |
| --- | --- |
| Framework | Next.js 14, React 18 |
| UI | MUI 5, Emotion, Tailwind CSS 3 |
| State | Redux Toolkit |
| Auth & DB | NextAuth.js 4, Prisma 5, SQLite |
| Charts / Tables | ApexCharts, Recharts, TanStack Table |
| Editor / Calendar / Maps | Tiptap, FullCalendar, Mapbox GL |

## Requirements

- Node.js 18.17 or newer (Node 20+ recommended)
- npm 9 or newer

## Getting Started

```bash
# 1. Clone the repository
git clone <your-repo-url>
cd academic-demo-main

# 2. Install dependencies (also runs `prisma generate` and builds icons)
npm install

# 3. Create your environment file
cp .env.example .env
```

Open `.env` and set at least:

```env
NEXTAUTH_SECRET=<random string, e.g. output of: openssl rand -base64 32>
DATABASE_URL="file:./dev.db"
# Optional, only for Google login
GOOGLE_CLIENT_ID=
GOOGLE_CLIENT_SECRET=
```

```bash
# 4. Create the database tables
npm run migrate

# 5. Start the dev server
npm run dev
```

Open [http://localhost:3000](http://localhost:3000). The root URL redirects to `/en/dashboards/crm`.

## Scripts

| Command | Description |
| --- | --- |
| `npm run dev` | Start the development server |
| `npm run build` | Create a production build |
| `npm start` | Run the production build |
| `npm run lint` / `lint:fix` | Lint the code (and auto-fix) |
| `npm run format` | Format code with Prettier |
| `npm run build:icons` | Regenerate `generated-icons.css` (Tabler icons) |
| `npm run migrate` | Run Prisma migrations |

## Environment Variables

See [`.env.example`](.env.example) for the full list: `BASEPATH`, `NEXT_PUBLIC_APP_URL`, `NEXTAUTH_URL`, `NEXTAUTH_SECRET`, `GOOGLE_CLIENT_ID`, `GOOGLE_CLIENT_SECRET`, `DATABASE_URL`, `API_URL`.

## Project Structure

```
src/
  app/          Routes (App Router) and API routes
  @core/        Core theme, settings and shared components
  @layouts/     Vertical and horizontal layouts
  @menu/        Navigation menu system
  components/   Reusable components and dialogs
  views/        Page-level views (dashboards, apps, forms, charts)
  prisma/       Prisma schema and migrations
  redux-store/  Redux slices
  fake-db/      Demo data used by the mock API
public/         Images and static assets
```

## Notes

- Package manager: this project uses **npm** (`package-lock.json`).
- `generated-icons.css` is generated automatically on install and is git-ignored.
- Never commit your `.env` file.

## License

The base template (Vuexy) is a commercial product. Check its license terms before publishing or redistributing.
