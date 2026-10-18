# Santa Letters purchase page

A single static page (`index.html`) with two options. Each "Choose" button opens a Stripe Payment Link. No server, no Stripe keys on the page.

## 1. Create the two Payment Links in Stripe

Dashboard → Payment Links → New. Make one per option.

- Under **After payment**, you can redirect back to your page or keep Stripe's confirmation.
- Under **Advanced options → Add custom fields**, collect what you need to write the letter (for example the child's name).
- Collect the shipping address if you mail the letters.

## 2. Edit `index.html`

Search for `REPLACE_WITH_OPTION_1_LINK` and `REPLACE_WITH_OPTION_2_LINK` and paste your two links (they look like `https://buy.stripe.com/...`). Change the names, prices and bullet points to match your products.

The price on the page is only text. Stripe charges what the Payment Link says, so keep them in sync.

## 3. Publish on GitHub Pages

1. On github.com, create a **public** repository named `santa-letters` (Pages on private repos needs a paid plan).
2. Upload `index.html` (Add file → Upload files → Commit).
3. Settings → Pages → Source: **Deploy from a branch**, Branch: `main`, folder `/ (root)` → Save.
4. After a minute the page is live at `https://cloudyrango.github.io/santa-letters/`.

## 4. QR code

`qr-code.png` (for printing on most things) and `qr-code.svg` (scales to any size) already point at
`https://cloudyrango.github.io/santa-letters/`.

If you use a different repository name or a custom domain, the QR code needs regenerating. Scan it with your phone after publishing to confirm it opens the page.

Because the QR points to your page rather than to Stripe, you can change prices or Payment Links later without reprinting it, as long as the repository name stays the same.
