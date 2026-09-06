# Apex Computers v1.7 — price, media and contact QA

Validation date: 6 September 2026

## Outcome

The consolidated buildless website passed all automated checks performed in this workspace: 27/27 Node tests plus the complete simulated shopping/contact flow.

## Catalogue and pricing

- 76/76 product records present and unique.
- 275/275 media records present and unique.
- All 76 product prices and every selectable variant price match the amounts in the supplied flyer, sales-listing artwork or directly supplied product details.
- The three new Microsoft Surface configurations retain the supplied prices of TSh 880,000, TSh 980,000 and TSh 1,180,000 and their distinct processor/RAM specifications.
- All prices are positive integers in TSh; every multi-configuration product uses its first variant as the displayed starting price.
- Customer-facing price labels now say “Price from your supplied listing · Confirm today” in English and “Bei kutoka kwenye tangazo lako · Thibitisha leo” in Kiswahili.
- The full product-by-product record and market spot check are in `PRICE-AND-MEDIA-AUDIT.md`.

## Images and flyers

- Every main image, thumbnail, product photo and flyer path resolves to a file in the package.
- The JSON catalogue and browser-ready `catalog.js` are exactly synchronized.
- Visual contact-sheet inspection found one incorrect mixed gallery. Five HP EliteBook x360 1040 G6 photos were removed from the HP EliteBook x360 1030 G7 listing, and their media search metadata now identifies only the 1040 G6.
- The corrected HP 1030 G7 gallery now contains only its seven matching photos, its own main image and its own flyer.
- The eight supplied Microsoft Surface photos are present, optimized and intentionally mapped to all three new Surface listings; each product card uses a different cover image.
- The Surface Laptop 4 i7 screen size is explicitly marked “Confirm size” because the submitted specification did not include it.
- Intentional shared artwork remains documented in the price/media audit.

## Design and mobile QA

- Four clear contact shortcuts are shown below the introduction: Call, WhatsApp, SMS and Email.
- The contact row uses four columns on desktop and a simple 2-by-2 layout on phones.
- Product cards remain two columns on normal phones and one column below 359 px.
- Key buttons and navigation controls retain 44 px or larger touch targets.
- Page IDs are unique, major controls have accessible labels, images have catalogue-derived alternative text, and keyboard focus styles remain present.
- The simulated browser flow loaded all three featured Surface cards, opened the Surface Laptop 4 i7 with all eight gallery photos, verified its price in WhatsApp/SMS, switched English to Kiswahili, opened a product by URL, changed a priced variant, opened the enquiry bag and verified its contact messages.

## Link and messaging QA

- Call links use `tel:+255746584214`.
- WhatsApp links use `https://wa.me/255746584214` with URL-encoded English or Kiswahili product/order text.
- Normal-message links use `sms:+255746584214?body=...` with the same selected product, configuration and price.
- Email contact links use `mailto:scbernard004@gmail.com`.
- Product variant changes update both the WhatsApp and SMS price/message.
- Bag quantity and variant details are included in both WhatsApp and SMS messages.
- All local HTML, CSS, JavaScript, font and product-media references resolve; no `javascript:` links are present.

Device note: `tel:`, `sms:`, `mailto:` and WhatsApp hand-off links open the matching app only when the device has a compatible dialler, messaging, mail or WhatsApp application. Their targets and generated message contents passed the simulated-browser checks; the external apps cannot be launched from this workspace.

## Gmail notification QA

- The enquiry API validates origin, JSON content, size, products, variants, quantities, customer fields, consent and the anti-spam honeypot.
- The server ignores client-supplied prices and rebuilds every item price from the audited server catalogue.
- A mocked successful delivery was addressed only to `scbernard004@gmail.com` and returned a valid `AC-YYYYMMDD-XXXXXXXX` reference.
- A Microsoft Surface Laptop 4 i7 enquiry was rebuilt from the server catalogue with the correct TSh 1,180,000 price and product details in the generated Gmail message.
- Mocked SMTP failure, missing configuration, invalid origin, invalid data, rate limiting and Turnstile failures all fail closed and never show a false success.
- When email is unavailable, the interface offers WhatsApp and SMS.

A real Gmail inbox delivery was not attempted because Gmail App Password and Vercel environment variables are private and are not stored in the package. After deployment, add the variables listed in `README.md`, redeploy, submit one enquiry and confirm receipt in Inbox/Spam before public launch.

## Packaging

- Plain HTML/CSS/JavaScript; no build command or output directory.
- `index.html` opens locally by double-clicking it.
- Vercel serverless email remains optional and does not block calls, WhatsApp or SMS.
- JavaScript syntax checks pass for the website and API files.
