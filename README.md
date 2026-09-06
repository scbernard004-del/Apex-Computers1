# Apex Computers — consolidated master website

A ready-to-upload static shop with 76 catalogue listings and 275 original photos, flyers and renders. This master project combines the website-development and setup/deployment work into one final package. See `PROJECT-SUMMARY.md` for the full consolidated record.

## Test it — no installation

1. Extract `Apex-Computers-Website.zip`.
2. Open the `apex-computers` folder.
3. Double-click `index.html`.

The catalogue, English/Kiswahili switching, dark/light mode, search, filters, favourites, comparison, photos, product selection, calls, SMS and WhatsApp ordering work immediately. Email enquiries work after deployment to Vercel and Gmail configuration.

Open `START-HERE.html` for the easiest illustrated-style instructions.

## Upload to GitHub using only your browser

This site contains many product images. GitHub currently accepts up to 100 files in one browser upload, so the media are already divided into small folders.

1. Sign in at [github.com](https://github.com/) and create a new empty repository named `apex-computers`.
2. In the empty repository, choose **uploading an existing file**. Later, use **Add file → Upload files**.
3. From Windows File Explorer, drag all the loose files plus the small `api`, `assets`, `data` and `lib` folders onto the GitHub upload page. Do not drag the ZIP file.
4. Enter `Add Apex Computers website` and commit the files.
5. Return to **Add file → Upload files** and upload `media-01`, `media-02` and `media-03` one folder at a time, committing after each folder.

Keep the same folder names and do not put the files inside an extra folder in the repository. When finished, `index.html`, `package.json` and `vercel.json` must be visible on the first page of the repository.

GitHub's official browser-upload guide: <https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository>

## Deploy from GitHub to Vercel — no build commands

1. Sign in at [vercel.com/new](https://vercel.com/new) with GitHub.
2. Import your `apex-computers` repository.
3. Choose **Framework Preset: Other**.
4. Leave **Root Directory** at the default.
5. Leave **Build Command** and **Output Directory** empty/default. Do not type `npm run build`.
6. Click **Deploy**.

The website is plain HTML, CSS and JavaScript, so Vercel publishes it directly. The small `package.json` is only for the optional Gmail enquiry function; Vercel installs that dependency automatically. You do not install Node.js, npm, Git, GitHub Desktop, Vercel CLI, VS Code or any build software.

Vercel's documentation confirms that a plain static site may need no build command: <https://vercel.com/docs/fundamentals/builds>

## Enable Gmail enquiry notifications

WhatsApp and SMS ordering work without Gmail setup. To also receive completed enquiry forms at `scbernard004@gmail.com`:

1. Turn on **2-Step Verification** for the Gmail account that will send the notifications.
2. Open [Google App Passwords](https://myaccount.google.com/apppasswords) and create an app password named `Apex Computers`.
3. In Vercel, open your project and go to **Settings → Environment Variables**.
4. Add these five names for Production:

| Name | Value |
|---|---|
| `SMTP_HOST` | `smtp.gmail.com` |
| `SMTP_PORT` | `465` |
| `SMTP_USER` | `scbernard004@gmail.com` |
| `SMTP_PASS` | The Google App Password |
| `NOTIFICATION_EMAIL` | `scbernard004@gmail.com` |

5. Redeploy the project, submit one test enquiry and check Inbox and Spam.

Never put the App Password in GitHub or any website file. Only store it in Vercel's Environment Variables. If Gmail is not configured, the website tells the customer to use WhatsApp or SMS and does not pretend that an email was sent.

## What customers can do

- Switch the complete interface between English and Kiswahili.
- Browse and search laptops, SSDs and printers.
- See photos, specifications and prices verified against the supplied listings, with a reminder to confirm today's price.
- Tap **Buy / Nunua** to send a product-specific WhatsApp order.
- Send the selected product or enquiry bag by normal SMS.
- Tap **Enquire / Uliza** to send a question through the optional email form.
- Save favourites and compare up to three products.

Orders and payments are confirmed directly with Apex Computers. The website does not collect online payments or automatically reserve stock.

## Important catalogue note

Prices and specifications came from supplied flyers and sales briefs. All 76 displayed prices were rechecked against those sources on 6 September 2026. Confirm present stock, condition, exact specification, price, warranty, payment and delivery before completing an order. See `PRICE-AND-MEDIA-AUDIT.md` for the full product-by-product price record and current-market spot check, and `ASSET-SOURCES.md` for the media inventory.
