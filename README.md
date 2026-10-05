# Attest: academic credentials, attested
Front-end prototype. Open `index.html`, or run `python3 -m http.server` here. No build step. All data is simulated in the browser (localStorage); no payments are taken and no email is sent (codes appear on screen).

## Pages
index (landing) · role (choose role) · auth (role-specific sign-up and sign-in) · dashboard (workspace per role)
js: config, store (data layer: the only file to swap for a backend), charts, print, auth, dashboard

## Demo accounts (password demo1234)
| Role | Sign in with |
|---|---|
| Institution | admin@kingsway.edu + registration number UNI-0142 (also admin@riverside.edu SCH-0204, admin@lakeview.edu COL-0087) |
| Credential owner | student@mail.com |
| Verifier | hr@acme.com |
| Regulator | audit@gov.org (sign-up code REG-2026) |
| Platform owner | owner@attest.app (sign-in only, link in footer) |

## Walk-through for a presentation
1. Landing page, then Register your institution (see its registration-number sign-in).
2. As Kingsway: Issue credentials, note the one-time code. Records shows codes for unclaimed credentials.
3. Sign up as an owner. Daniel Mwangi: Kingsway University, S-1002, born 2000-09-03, code 482913. An unregistered institution name is rejected.
4. Owner: copy the share code, try hardcopy (needs Hardcopy Plus), request it, then approve it as the institution and download.
5. As verifier: verify a share code, print the report. Try a fake code three times.
6. As regulator: Audit overview, Event log (filter, export), Institutions, Clear hold.
7. As platform owner: revenue, accounts, price editing, backend connection table.

## Scaling notes
UI never reads storage directly; swap Store methods for REST calls via CONFIG.api. Tables are paginated (CONFIG.pageSize). Audit events carry institution, risk and reasons, ready for server-side filtering. Plans, prices and quotas are data, not code.
