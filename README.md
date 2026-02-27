![Mercur Main Cover](https://cdn.prod.website-files.com/6790aeffc4b432ccaf1b56e5/67a225dc6fa298afc1cc4ae6_Mercur%20Cover.png)

<div align="center">
  <h1>Mercur <br> Open Source Marketplace Platform</h1> 
  <a href="https://github.com/mercurjs/mercur/tree/main?tab=MIT-1-ov-file">
    <img alt="License" src="https://img.shields.io/badge/license-MIT-blue.svg" />
  </a>
  <a href="#">
    <img alt="PRs Welcome" src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg" />
  </a>
  <a href="https://rigbyjs.com/#contact">
    <img alt="Support" src="https://img.shields.io/badge/support-contact%20author-blueviolet.svg" />
  </a>
  <p>
    <a href="https://mercurjs.com/">Mercur</a> | <a href="https://docs.mercurjs.com/">Docs</a>
  </p> 
</div>

# What is Mercur?

<a href="https://www.mercurjs.com/">Mercur</a> is an open source marketplace platform that combines the simplicity of SaaS with the flexibility and ownership of self-hosting. Built on <a href="https://github.com/medusajs/medusa">MedusaJS</a>, it enables businesses to launch and scale fully customizable marketplaces.

Mercur allows you to start, customize, manage, and scale your marketplace using a modern and developer-friendly stack.

## Mercur 1.0

Mercur 1.0 is production-ready for B2C marketplaces and fully open source. It includes:

- Vendor system  
- Admin panel  
- B2C storefront  
- Self-hosted infrastructure with full data ownership  

Read more in the official release announcement:  
https://www.mercurjs.com/updates/mercur-1-0-release

## Why Choose Mercur?

- Full ownership with no vendor lock-in  
- Modern architecture powered by MedusaJS  
- Customizable storefronts and workflows  
- Built-in marketplace logic  

## Marketplace Capabilities

- Custom B2B marketplace  
- Custom B2C marketplace  
- eCommerce-to-marketplace extension (coming soon)

![Mercur Use Cases](https://cdn.prod.website-files.com/6790aeffc4b432ccaf1b56e5/67b46aa08180d5b8499c6a15_Use-cases.jpg)

# Marketplace Components

**Storefront**  
Customizable marketplace storefront supporting multi-vendor checkout.

B2C Storefront Repository:  
https://github.com/mercurjs/b2c-marketplace-storefront  
Demo: https://b2c.mercurjs.com/

**Admin Panel**  
Full control over products, categories, vendors, commissions, and rules.

**Vendor Panel**  
Dashboard for sellers to manage products, orders, and stores.

Repository: https://github.com/mercurjs/vendor-panel  

**Integrations**

- Stripe  
- Adyen  
- Resend  
- Algolia  
- TalkJS  

![Mercur](https://cdn.prod.website-files.com/6790aeffc4b432ccaf1b56e5/67a1020f202572832c954ead_6b96703adfe74613f85133f83a19b1f0_Fleek%20Tilt%20-%20Readme.png)

---

# Installation (Local Development)

### 1. Clone the repository

```bash
git clone https://github.com/checkatrade-labs/shop-mercur
cd shop-mercur
yarn
```

---

### 2. Requirements

- Node.js v20.x  
- Yarn 1.22.x  
- Docker (PostgreSQL running in Docker)  
- Redis (optional)  

Tested versions:

- Node: v20.x  
- Yarn: 1.22.x  

---

### 3. Environment Variables

Create a `.env` file in the root and configure:

```env
LOG_LEVEL=debug

STORE_CORS=http://localhost:3000
ADMIN_CORS=http://localhost:9000,http://localhost:9001,http://localhost:5173,http://localhost:5174
VENDOR_CORS=http://localhost:5173,http://localhost:5174
AUTH_CORS=http://localhost:9000,http://localhost:9001,http://localhost:5173,http://localhost:3000,http://localhost:5174

REDIS_URL=redis://localhost:6379

JWT_SECRET=supersecret1
COOKIE_SECRET=supersecret1

DATABASE_URL=postgres://postgres:postgres@localhost:5432/mercurjs
DB_NAME=mercurjs

STRIPE_SECRET_API_KEY=sk_test_secret_key
STRIPE_CONNECTED_ACCOUNTS_WEBHOOK_SECRET=whsec_secret_key

ADYEN_MERCHANT_ACCOUNT=CAT-Shop
ADYEN_THEME_ID=theme_id_secret_key
ADYEN_PAYMENT_API_KEY=payment_api_key_secret_key
ADYEN_PLATFORM_API_KEY=platform_api_key_secret_key
ADYEN_LEGAL_API_KEY=legal_api_key_secret_key
ADYEN_URL_PREFIX=url_prefix_secret_key
ADYEN_ENVIRONMENT=TEST
ADYEN_HMAC_SECRET=hmac_secret_key
ADYEN_ALLOWED_PAYMENT_METHODS="visa,mc,amex"

RESEND_API_KEY=resend_api_key_secret_key
RESEND_FROM_EMAIL=no-reply@shop.checkatrade.com

ALGOLIA_APP_ID=algolia_app_id_secret_key
ALGOLIA_API_KEY=algolia_api_key_secret_key

VITE_TALK_JS_APP_ID=xxx
VITE_TALK_JS_SECRET_API_KEY=xxx

# Used in notifications
VENDOR_PANEL_URL=http://localhost:5173
ADMIN_PANEL_URL=http://localhost:8000
STOREFRONT_URL=http://localhost:7001
BACKEND_URL=http://localhost:9000
```

Ensure PostgreSQL is running via Docker before proceeding.

---

### 4. Build the project

From the root folder:

```bash
yarn install
yarn build
```

---

### 5. Setup database

```bash
cd apps/backend
npx medusa db:create
npx medusa db:migrate
```

---

### 6. Seed data

```bash
yarn seed
```

The seed script outputs:

- Example user credentials  
- Publishable key required for the storefront  

---

### 7. Run backend

```bash
cd apps/backend
yarn dev
```

The backend will start in development mode.

---

# Resources

Mercur Website:  
https://www.mercurjs.com/

Mercur Docs:  
https://docs.mercurjs.com/introduction

Medusa Website:  
https://www.medusajs.com/

Medusa Docs:  
https://docs.medusajs.com/v2