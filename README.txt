MYCO MARKET — GLOBAL, EMPTY CATALOG EDITION

WHAT IS INCLUDED
- Public storefront with a mushroom-themed landing illustration.
- Product catalogue starts EMPTY. No products or prices are preloaded.
- Registration country selector includes the global ISO country list.
- Phone numbers must be entered in international E.164 format (example +2348012345678).
- Currency selector supports NGN, USD, GBP, EUR, CAD, AUD, GHS, KES, ZAR and INR.
- Private admin page at /admin.html to add products, upload images, and delete products.
- Email OTP backend: six digits, 5-minute expiry, 5 attempts, resend cooldown.

IMPORTANT ABOUT PRICES
Each product price is entered by the owner in the currency selected for that product. This version does NOT automatically convert prices using live exchange rates. The storefront starts blank until you add products. If you need automatic exchange-rate conversion later, configure a reliable FX-rate API.

LOCAL SETUP
1. Install Node.js 20+ on a computer or Node-capable host.
2. Extract this ZIP and open this folder in a terminal.
3. Run npm install.
4. Copy .env.example to .env.
5. Set SESSION_SECRET to a random secret of at least 32 characters.
6. Set ADMIN_PASSWORD to a strong private password.
7. For local-only testing set DEV_OTP_MODE=true and NODE_ENV=development.
8. Run npm start and open http://localhost:3000.
9. Test registration. In local test mode the OTP appears in the server terminal; it is NOT emailed.
10. Open http://localhost:3000/admin.html, sign in with ADMIN_PASSWORD, add a product and optionally upload its image.

REAL EMAIL VERIFICATION FOR OTHER PEOPLE
1. Choose an email provider or SMTP mailbox that permits transactional email. A free tier may have limits.
2. Verify the sender address/domain with that provider.
3. Put SMTP_HOST, SMTP_PORT, SMTP_SECURE, SMTP_USER, SMTP_PASS and MAIL_FROM in .env.
4. Set NODE_ENV=production and DEV_OTP_MODE=false. Never expose SMTP credentials in public files.
5. Deploy the Node.js server on a host that supports Node.js and persistent storage.
6. Use HTTPS and a persistent database/session store for production. SQLite requires a persistent disk; otherwise use a managed database.
7. Open the live website, register with a real email you can access, retrieve the six-digit code from that inbox, enter it, and confirm the account is verified.

GLOBAL PHONE NUMBER
Enter the full country calling code, e.g. +234 for Nigeria, +1 for US/Canada, +44 for UK. Do not assume country selection automatically adds a phone prefix; type the full international number.

SECURITY NOTES
- Do not use DEV_OTP_MODE on a public website.
- Use a unique long ADMIN_PASSWORD and SESSION_SECRET.
- Configure HTTPS, persistent session storage, backups, monitoring and security review before public launch.
- The admin page is not linked in the public navigation, but its URL is discoverable; security is enforced by server-side login.
- This starter uses a simple admin password comparison; for a high-traffic production shop, add admin password hashing, CSRF protection, audit logs and stronger session storage.
