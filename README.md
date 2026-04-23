# Black Sherpa Manufacturing OS

Advanced Manufacturing Operating System for PT Black Sherpa. Built with Next.js 15, Prisma, Supabase, and NextAuth v5.

## 🚀 Features

- **RBAC (Role-Based Access Control)**: 7 unique roles with distinct dashboards and permissions.
- **Job Order Management**: End-to-end workflow from material picking to shipping.
- **Real-time Inventory**: Stock monitoring and low stock alerts.
- **Production Analytics**: Executive dashboard with efficiency tracking and revenue forecast.
- **Audit Logs**: Full traceability of all system actions.

## 🛠 Tech Stack

- **Framework**: Next.js 15 (App Router)
- **Database**: PostgreSQL (via Supabase)
- **ORM**: Prisma
- **Auth**: NextAuth.js v5 (Auth.js)
- **UI**: Tailwind CSS + shadcn/ui + Framer Motion
- **Deployment**: Vercel

## 📦 Deploy to Vercel + Supabase

Follow these steps to deploy the application to production:

### 1. Supabase Setup
1. Create a new project on [Supabase](https://supabase.com).
2. Go to **Project Settings > Database** and get your connection strings.
   - Use **Transaction Mode** (port 6543) for `DATABASE_URL`.
   - Use **Session Mode** (port 5432) for `DIRECT_URL`.
3. Get your `NEXT_PUBLIC_SUPABASE_URL` and `NEXT_PUBLIC_SUPABASE_ANON_KEY` from **Project Settings > API**.

### 2. Vercel Deployment
1. Connect your GitHub repository to [Vercel](https://vercel.com).
2. Use the **Supabase Integration** on Vercel or manually add the following environment variables:
   - `DATABASE_URL`
   - `DIRECT_URL`
   - `NEXT_PUBLIC_SUPABASE_URL`
   - `NEXT_PUBLIC_SUPABASE_ANON_KEY`
   - `NEXTAUTH_SECRET` (Generate with `openssl rand -base64 32`)
   - `NEXTAUTH_URL` (Your production URL)
   - `AUTH_SECRET` (Same as `NEXTAUTH_SECRET`)

### 3. Initialize Database
After deployment, run the following commands to set up your database schema and initial data:

```bash
# Push schema to Supabase
npx prisma db push

# Seed initial division accounts
npx prisma db seed
```

## 📋 Division Accounts (Initial Seed)

| Role | Email | Password |
|------|-------|----------|
| Super Admin | superadmin@blacksherpa.id | admin123 |
| Admin Produksi | admin.produksi@blacksherpa.id | admin123 |
| PIC Potong | potong@blacksherpa.id | admin123 |
| PIC Produksi | produksi@blacksherpa.id | admin123 |
| PIC QC | qc@blacksherpa.id | admin123 |
| PIC Seal | seal@blacksherpa.id | admin123 |
| PIC Pengiriman | pengiriman@blacksherpa.id | admin123 |

## 🛠 Development

```bash
npm install
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.
