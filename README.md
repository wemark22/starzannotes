# StarzanNotes

Full-stack Test Series Platform for Indian Competitive Exams (JEE, NEET, CUET, SSC, UPSC, and Foundation) with dedicated Student and Admin panels, powered by a Supabase PostgreSQL backend.

---

## 📁 Repository Structure

```text
starzannotes/
├── student/
│   └── index.html      # Complete Student Web Application (Single-File App)
├── admin/
│   └── index.html      # Comprehensive Admin & Teacher Control Panel
└── README.md           # Project Documentation
```

---

## 🚀 Live Panels

- **Student App**: [`/student/index.html`](student/index.html)
  - Interactive exam series browser (JEE, NEET, Foundation, CUET).
  - Subject/Chapter/Topic tree hierarchy with live search & filters.
  - Realistic CBT (Computer Based Test) simulation environment with marking scheme, countdown timer, question palette, review status, and instant feedback.
  - Test result analysis, solution review with explanations, and real-time percentile/leaderboard.
  - Coupon redemption, dynamic banners, and question reporting system.
  - Google OAuth Sign-in & instant Demo Sign-in fallback.

- **Admin Control Panel**: [`/admin/index.html`](admin/index.html)
  - Secured Admin authentication gate (Demo login: any email with `admin`, password `admin123`).
  - Analytics dashboard: gross sales, refunds, net sales, order counts, live test count, and total attempts.
  - Complete Test & Question Builder: Create, duplicate, delete, and publish tests with custom time limits, marks, and negative markings. Bulk question importer.
  - Coupon manager: percentage or flat discount codes with validity dates, max usage limits, and toggle status.
  - Banner manager: promotional banners with custom click actions (target test or external URL) and scheduling.
  - Student moderation: view history, warn, suspend, or ban students.
  - Question dispute & error reporting resolution workflow (re-score, credit marks, drop question, dismiss).
  - Staff management with role-based permissions (Owner, Creator, Reviewer, Support).
  - Global app settings, Razorpay credentials, contact info, and maintenance mode toggle.

---

## ⚡ Supabase Backend Architecture

All data is synchronized with Supabase PostgreSQL in real-time.

### Database Tables:
1. `config` — App name, brand assets, maintenance mode status, contact info, razorpay keys.
2. `series` — Exam series classifications (e.g. JEE Main, NEET UG, Foundation).
3. `nodes` — Hierarchical chapter/topic tree nodes for organized test discovery.
4. `tests` — Test metadata, instructions, pricing, duration, total marks, status.
5. `questions` — Question content, options, correct answers, explanations, tags, marks.
6. `attempts` — Student test attempts, chosen responses, marks, time spent, score breakdown.
7. `banners` — Promotional and announcement banners displayed in the student app.
8. `coupons` — Promotional codes and discount values.
9. `orders` — Student purchases and transactions.
10. `reports` — Student dispute reports on question keys or typos.
11. `staff` — Team members and access permission lists.
12. `users` — Student profiles and account statuses.

---

## 🔑 Authentication & Demo Credentials

- **Student Login**: Click "Sign in with Google" or "Continue as Demo Student".
- **Admin Login**:
  - Email: `admin@starzannotes.in` (or any email containing `admin`)
  - Password: `admin123`

---

## 🛠️ Deployment

Both `student/index.html` and `admin/index.html` are zero-build, self-contained standalone HTML applications that load dependencies via CDN (Supabase JS Client v2). They can be hosted on GitHub Pages, Vercel, Netlify, Cloudflare Pages, or any static web server.
