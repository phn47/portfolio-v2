# 🚀 Portfolio V2 – Phạm Hoài Nam

Hello everyone! 👋  
I'm **Phạm Hoài Nam**, and I'm excited to introduce my personal portfolio website — a showcase of my projects, skills, and certifications, built entirely with modern web technologies.

### 🌐 Live Demo  
👉 [Visit the Website](https://portfolio-phn.vercel.app/)

---

## 🧰 Tech Stack

This portfolio is built with the following technologies:

- **React.js** – UI library for building responsive components  
- **Tailwind CSS** – Utility-first CSS framework for rapid styling  
- **Supabase** – Backend-as-a-Service for data, certificates, and comments  
- **Framer Motion** – Smooth animations and transitions  
- **AOS (Animate On Scroll)** – Scroll-based animations  
- **Lucide** – Icon library  
- **Material UI** – Pre-built React UI components  
- **SweetAlert2** – Elegant modal dialogs

---

## ⚙️ Prerequisites

Make sure the following are installed on your system:

- **Node.js** (v14 or higher)  
- **npm** or **yarn** package manager

---

## 🚀 Getting Started

To run the project locally, follow these steps:

### 1. Clone the Repository

```bash
git clone https://github.com/phn47/portfolio-v2.git
cd portfolio-v2
```

### 2. Install Dependencies

```bash
npm install
# Or if there are dependency conflicts:
npm install --legacy-peer-deps
```

### 3. Start the Development Server

```bash
npm run dev
```

Visit the app at `http://localhost:5173` in your browser.

---

## 🏗️ Build for Production

To generate a production-ready build:

```bash
npm run build
```

The output will be placed in the `dist` directory — ready to be deployed.

---

## 🚀 Deploying to Vercel

[Vercel](https://vercel.com/) is a cloud platform for frontend frameworks like React. Here's how to deploy your portfolio:

### 1. Push Your Code to GitHub

```bash
git init
git remote add origin https://github.com/your-username/portfolio-v2.git
git add .
git commit -m "Initial commit"
git push -u origin main
```

> Replace `your-username` with your actual GitHub username.

### 2. Deploy via Vercel Dashboard

1. Go to [https://vercel.com](https://vercel.com) and sign in with your GitHub account.
2. Click **"New Project"** and select your portfolio repository.
3. Configure project settings:
   - **Framework**: `Vite`
   - **Build Command**: `npm run build`
   - **Output Directory**: `dist`
4. Under **Environment Variables**, add:
   - `VITE_SUPABASE_URL`
   - `VITE_SUPABASE_ANON_KEY`
5. Click **Deploy**.

Your portfolio will be live shortly!

### ✅ Automatic CI/CD

Once deployed, every time you push changes to the `main` branch, Vercel will automatically rebuild and redeploy your site.

---

## 🧩 Supabase Configuration

This project uses **Supabase** to manage portfolio content, certificates, and comments.

### 1. Create a Supabase Project

- Go to [supabase.com](https://supabase.com) and create a new project.
- Retrieve your **Project URL** and **Anon Public Key** from **Settings → API**.

### 2. Set Up Tables & Policies

Use the following SQL script in **Supabase SQL Editor** to create tables, configure row-level security, and insert sample data.

<details>
<summary>Click to Expand SQL Script</summary>

```sql
-- Projects Table
CREATE TABLE public.projects (...);

-- Certificates Table
CREATE TABLE public.certificates (...);

-- Comments Table
CREATE TABLE public.portfolio_comments (...);

-- Enable RLS
ALTER TABLE public.projects ENABLE ROW LEVEL SECURITY;
ALTER TABLE public.certificates ENABLE ROW LEVEL SECURITY;
ALTER TABLE public.portfolio_comments ENABLE ROW LEVEL SECURITY;

-- Policies and Storage omitted for brevity...
```
</details>

### 3. Enable Realtime (Comments)

- Go to **Table Editor > portfolio_comments**.
- Enable **Realtime** updates.

---

## 🔐 Environment Variables

Create a `.env` file in the root of your project and add:

```env
VITE_SUPABASE_URL=your-supabase-url
VITE_SUPABASE_ANON_KEY=your-supabase-anon-key
```

> ⚠️ Note:  
> - All Vite environment variables must begin with `VITE_`  
> - Never commit your `.env` file — add it to `.gitignore`  

---

## 📁 Supabase Client Setup

Make sure the `src/supabase.js` file initializes the client correctly:

```js
import { createClient } from '@supabase/supabase-js'

const supabaseUrl = import.meta.env.VITE_SUPABASE_URL
const supabaseKey = import.meta.env.VITE_SUPABASE_ANON_KEY

if (!supabaseUrl || !supabaseKey) {
  throw new Error("Supabase credentials missing. Check your .env file.")
}

export const supabase = createClient(supabaseUrl, supabaseKey)
```

---

## 🛠 Troubleshooting

- Ensure Node.js and npm are installed correctly
- Confirm that `.env` is properly configured
- Restart the dev server after setting environment variables
- Check for console/network errors in the browser
- Clear your browser cache if necessary

---

## 🙏 Credits & License

If you find this project useful, please give it a ⭐ on GitHub.  
Feel free to use or extend it with proper attribution. Thanks for your support!

---

## 📬 Contact

**Phạm Hoài Nam**

- 🌐 Website: [portfolio-phn.vercel.app](https://portfolio-phn.vercel.app)  
- 🐙 GitHub: [github.com/phn47](https://github.com/phn47)