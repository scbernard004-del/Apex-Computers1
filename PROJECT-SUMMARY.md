# Apex Computers Website — consolidated master project

This is the single master project created from the Apex Computers website-development and website setup/deployment work. It replaces the earlier separate website packages while preserving the completed catalogue, media, customer features and deployment setup.

## Business details

- Business name: Apex Computers
- Market: Tanzania
- Call, WhatsApp and SMS: 0746 584 214 / +255 746 584 214
- Enquiry notifications: scbernard004@gmail.com
- Website credit: Isaac Sabuni

## Included website work

- Mobile-first online catalogue with a simple buy and enquiry journey.
- Complete English and Kiswahili interface switching.
- Dark and light themes for desktop and mobile.
- 76 product listings with prices, specifications, variants and availability reminders.
- 275 unique original product photos, promotional flyers and renders gathered from the supplied work.
- Laptops, MacBooks, workstations, 2-in-1 devices, all-in-one computers, SSD storage and printers.
- Product search, brand/budget/RAM filters, sorting, favourites and comparison.
- Product detail views, photo/flyer gallery and downloadable original artwork.
- WhatsApp and normal SMS buying messages that include the selected product and configuration.
- Optional Gmail notification form for Vercel, including validation, consent, spam protection and safe fallback to WhatsApp or SMS.
- Responsive navigation and readable buttons for phones, tablets and computers.
- Historical-price, stock, condition, warranty, delivery and payment confirmation notices.

## Combined setup and deployment work

- `index.html` is in the project root and opens locally by double-clicking it.
- No local installation of Node.js, npm, Git, GitHub Desktop, Vercel CLI or an editor is required.
- Files are arranged for upload through the GitHub website.
- The 275 media files are divided between `media-01`, `media-02` and `media-03`, each below GitHub's 100-file browser-upload limit.
- Vercel uses Framework Preset `Other`, with no build command and no output-directory setting.
- Gmail credentials stay private in Vercel Environment Variables and are never included in GitHub.
- `START-HERE.html` and `README.md` contain the complete local-test, GitHub, Vercel and Gmail instructions.

## Consolidation decision

The earlier Easy GitHub/Vercel package used three compressed asset packs and build scripts. The master project keeps the later, simpler structure: the unique optimized WebP images are already in normal media folders, duplicate thumbnails have been removed, and no build step is required. This gives one project that works both offline and after GitHub/Vercel deployment.

## Verification completed

- All 76 products and 275 media records are present.
- All 76 catalogue and variant prices match their supplied flyer or sales-listing details.
- The three Microsoft Surface offers retain their distinct specifications and prices while intentionally sharing the same eight supplied product photos.
- Every catalogue image path resolves.
- The incorrect HP 1040 G6 photos were removed from the HP 1030 G7 gallery.
- English/Kiswahili shopping and enquiry flows pass.
- Product selection survives language switching.
- Selected variants and prices are retained without duplicate basket entries.
- Search, comparison, validation, offline fallback and mocked Gmail success paths pass.
- JavaScript syntax and ZIP integrity checks pass.

See `QA-REPORT.md` for the technical validation record and `PRICE-AND-MEDIA-AUDIT.md` for the complete price and media review.
