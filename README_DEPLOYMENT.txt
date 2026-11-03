EZELEX ENTERPRISE — ADVANCED MANAGEMENT CENTRE (SEPARATE BUILD)

PURPOSE
This is a separate upgrade build. It does NOT overwrite your currently working Management Centre files.

FILES
- index.html: copy of the corrected working Management Centre shell with PWA metadata and service-worker registration.
- admin-operations.html: copy of the latest operations file plus a separate advanced workspace layer.
- manifest.webmanifest, service-worker.js, ezelex-icon.svg: PWA install/offline-shell support.

DEPLOYMENT
1. Create a NEW GitHub repository for testing, or a separate staging branch/site.
2. Upload ALL five files to the repository root, preserving filenames.
3. Configure GitHub Pages and a staging hostname; do not change the current management.ezelexenterprise.com DNS/CNAME.
4. Test sign-in, every menu route, every data panel, worker/driver messaging, and all approval/payment flows before considering promotion.

SAFETY / LIMITS
- Existing Supabase auth and data calls are preserved in the copied HTML.
- The service worker caches only the static app shell; it deliberately does not cache Supabase auth, REST, or Edge Function responses.
- PWA install/offline shell is implemented. Browser notification permission and service-worker push display handling are included. Actual server-originated push delivery is NOT activated: it requires VAPID public/private keys, a subscription storage table, and a secured sender Edge Function. Do not describe remote push as live until those are configured and tested.
- Drag/drop card layout, per-device preferences, dark/light mode and compact layout are implemented.
- Analytics use the existing live operational data panels/charts; no synthetic financial values are generated.
- This is a static build check only. Live Supabase and email delivery must be tested in staging.

ROLLBACK
Your existing repository and existing HTML files remain untouched. To roll back, simply continue using the existing Management Centre URL/repository.
