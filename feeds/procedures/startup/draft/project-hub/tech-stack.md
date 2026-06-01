# [Platform] — Tech Stack & Technical Decisions

**Project:** [Platform] (e-commerce marketplace)
**Document type:** Engineering — stack & decisions
**Status:** 🚧 Draft (decisions to be confirmed by the team)

> Records the platform's technology choices and the reasoning behind them, so decisions aren't re-litigated. Owned by [Developer], reviewed by [Lead]. Items marked **(decide)** are open.

---

## 1. Platform Approach

The core question: **build a marketplace from scratch, or adopt an open-source e-commerce framework?**

| Option | Pros | Cons |
|:-------|:-----|:-----|
| **E-commerce framework** (e.g. Vendure, Medusa, Saleor) | Faster to MVP, multi-vendor & order/payment features built in, maintained | Learning curve, must fit our model, customization limits |
| **Build from scratch** | Full control, exact fit | Slow, expensive, reinvents solved problems |

> **(decide)** Strong lean toward an open-source framework for speed. **Vendure** was raised by the team as a candidate — evaluate it against the multi-vendor requirement (Vendure is single-seller by default and needs a plugin/extension for marketplace/multi-vendor).

## 2. Proposed Stack *(draft — confirm)*

| Layer | Choice | Notes |
|:------|:-------|:------|
| E-commerce core | **(decide)** Vendure / Medusa / custom | Must support multi-vendor, orders, inventory |
| Backend | _TBD_ (follows framework) | |
| Frontend / storefront | _TBD_ | Web-first per user stories |
| Database | _TBD_ (e.g. PostgreSQL) | |
| Auth | Email + OTP (per user stories) | |
| Payments | **(decide)** local + card provider | Must support seller payouts/withdrawals |
| Hosting / infra | _TBD_ | |
| Analytics | **Google Analytics** (confirmed in meeting notes) | Track website visitors |
| File/image storage | _TBD_ | Product & store images, verification photos |

## 3. Key Technical Requirements (from user stories)
- **Multi-vendor** stores, each with products & inventory
- **Buyer flow:** register (email+OTP), browse/search, cart, checkout, order tracking, reviews
- **Seller flow:** verification/KYC, store creation, product/order management, **weekly payouts**
- **Admin:** seller approval, category management, order oversight, financial reports
- **Payments + payout/withdrawal** engine with transaction records
- **KYC / identity verification (decide)** — required for sellers? buyers? (see [Legal Lead] / [todo.md](./todo.md))

## 4. Data & Privacy (engineering responsibilities)
- Store **PII** (name, DOB, phone, address, bank details, verification photos) securely — encryption at rest/in transit
- Minimize and protect health-related or sensitive data (flagged as a legal risk — see [risk-register.md](./risk-register.md))
- Define data-retention periods (e.g. receipts — open legal question)
- Access controls for admin/financial data

## 5. Open Decisions
- [ ] E-commerce framework vs. custom (and which framework)
- [ ] Payment & payout provider
- [ ] Hosting/infrastructure
- [ ] KYC requirement & provider
- [ ] Data-retention policy (technical implementation)

---

*Internal working document · `startup/draft/project-hub/`*
