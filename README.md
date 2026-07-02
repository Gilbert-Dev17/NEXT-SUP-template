# Next.js + Supabase Starter Template

A personal full-stack starter template built with Next.js, Supabase, Tailwind CSS, and shadcn/ui. Designed to eliminate repetitive project setup and enforce a consistent, scalable folder structure across projects.

---

## Tech Stack

| Technology | Purpose |
|---|---|
| [Next.js 16](https://nextjs.org/) | React framework with App Router |
| [TypeScript](https://www.typescriptlang.org/) | Type safety |
| [Tailwind CSS v4](https://tailwindcss.com/) | Utility-first styling |
| [shadcn/ui](https://ui.shadcn.com/) | Component library (Nova preset, Radix UI) |
| [Supabase](https://supabase.com/) | Backend-as-a-Service (Auth, Database, Storage) |
| [GraphQL](https://graphql.org/) + [graphql-request](https://github.com/graphql-request/graphql-request) | Lightweight GraphQL fetching client |
| [TanStack Query](https://tanstack.com/query/latest) | Client-side data fetching and caching |
| [React Hook Form](https://react-hook-form.com/) + [Zod](https://zod.dev/) | Form handling and schema validation |
| [next-themes](https://github.com/pacocoursey/next-themes) | Dark/light mode theming |
| [motion](https://motion.dev/) | Animation library for React |
| [pnpm](https://pnpm.io/) | Fast, disk-efficient package manager |

---

## How to Use This Template

1. Click the **"Use this template"** button at the top of this repository
2. Name your new repository and select its visibility
3. Clone your new repository locally:

```bash
git clone https://github.com/your-username/your-new-project.git
cd your-new-project
```

4. Install dependencies:

```bash
pnpm install
```

5. Set up your environment variables (see [Environment Variables](#environment-variables))

6. Start the development server:

```bash
pnpm dev
```

---

## Features Included

This template includes pre-configured setup for:

- **GraphQL client** — `graphql-request` with `src/lib/graphqlClient.ts`
- **Data fetching** — `@tanstack/react-query` with `src/lib/queryClient.ts` and `src/components/Providers.tsx`
- **Animations** — `motion` (Framer Motion) with example in `src/components/ui/MotionExample.tsx`
- **Form handling** — `react-hook-form` + `zod` + `@hookform/resolvers` for type-safe form validation
- **Dark mode** — `next-themes` with system preference detection and a ready-to-use `ThemeToggle` component at `src/components/shared/ThemeToggle.tsx`
- **shadcn/ui components** — `button`, `input`, `label`, `card`, `sonner` (toast notifications)
- **Demo route** — `/demo` showcasing the GraphQL query and animated UI together

---

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) v18 or higher
- [pnpm](https://pnpm.io/installation) installed globally
- A [Supabase](https://supabase.com/) project

### Installation

```bash
# Install dependencies
pnpm install

# Copy the environment variable template
cp .env.example .env.local
```

Fill in your Supabase credentials and GraphQL endpoint in `.env.local` (see [Environment Variables](#environment-variables)), then run the development server:

```bash
pnpm dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

---

## Folder Structure

```
├── public/                     # Static assets (images, icons, fonts)
├── src/
│   ├── app/                    # Next.js App Router
│   │   ├── (auth)/             # Authentication route group
│   │   │   ├── sign-in/         # Sign-in page
│   │   │   └── sign-up/         # Sign-up page
│   │   ├── (dashboard)/        # Dashboard route group
│   │   │   ├── layout.tsx      # Dashboard layout
│   │   │   └── page.tsx        # Dashboard home page
│   │   ├── globals.css         # Global styles and Tailwind imports
│   │   ├── layout.tsx          # Root layout
│   │   └── page.tsx            # Home page
│   ├── components/
│   │   ├── Providers.tsx       # App providers (ThemeProvider, QueryClientProvider)
│   │   ├── ui/                 # shadcn/ui components (auto-generated)
│   │   │   ├── button.tsx      # Button component
│   │   │   ├── card.tsx        # Card component
│   │   │   ├── input.tsx       # Input component
│   │   │   ├── label.tsx       # Label component
│   │   │   ├── sonner.tsx      # Toast notifications (Sonner)
│   │   │   └── MotionExample.tsx # Motion animation example
│   │   └── shared/             # Reusable custom components
│   │       └── ThemeToggle.tsx  # Dark/light mode toggle
│   ├── config/
│   │   └── constants/          # App-wide constants (routes, endpoints, etc.)
│   ├── hooks/                  # Custom React hooks
│   ├── lib/
│   │   ├── actions/            # Server actions
│   │   ├── services/           # Business logic and API services
│   │   ├── supabase/           # Supabase client configuration
│   │   │   ├── client.ts       # Browser-side Supabase client
│   │   │   ├── server.ts       # Server-side Supabase client
│   │   │   ├── queries.ts      # Database query functions
│   │   │   └── proxy.ts        # Middleware/proxy Supabase client
│   │   ├── graphqlClient.ts    # GraphQL request client
│   │   ├── queryClient.ts     # TanStack Query client
│   │   └── utils.ts            # Utility functions (cn function, etc.)
│   ├── types/                  # Global TypeScript types and interfaces
│   └── utils/                  # Custom helper functions
├── .env.example                # Environment variable template
├── components.json             # shadcn/ui configuration
├── eslint.config.mjs           # ESLint configuration
├── next.config.ts              # Next.js configuration
├── postcss.config.mjs          # PostCSS configuration
├── proxy.ts                    # Proxy configuration
├── pnpm-workspace.yaml         # pnpm workspace configuration
├── tailwind.config.ts          # Tailwind CSS configuration
└── tsconfig.json               # TypeScript configuration
```

---


## Environment Variables

Copy `.env.example` to `.env.local` and fill in the required values:

```bash
cp .env.example .env.local
```

| Variable | Description | Where to Find |
|---|---|---|
| `NEXT_PUBLIC_SUPABASE_URL` | Your Supabase project URL | Supabase Dashboard → Project Settings → API |
| `NEXT_PUBLIC_SUPABASE_ANON_KEY` | Your Supabase anonymous public key | Supabase Dashboard → Project Settings → API |
| `NEXT_PUBLIC_GRAPHQL_ENDPOINT` | GraphQL API URL for `graphql-request` | Your GraphQL server or proxy endpoint |

> **Note:** Never commit `.env.local` to version control. It is already included in `.gitignore`.

---

## Adding shadcn Components

This template uses the **Nova** preset with **Radix UI**. Add new components using:

```bash
pnpm dlx shadcn@latest add <component-name>
```

Example:

```bash
pnpm dlx shadcn@latest add dialog
pnpm dlx shadcn@latest add input
pnpm dlx shadcn@latest add card
```

Components are automatically placed in `src/components/ui/`.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.