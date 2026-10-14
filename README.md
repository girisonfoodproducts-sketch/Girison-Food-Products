# Girison Food Products — Assam Royal Tea Android App

Native Android app (Java) that fetches the live catalogue from the existing website API and provides a designed home screen, Leaf/Dust filters, product pricing, cart quantity controls, and WhatsApp order-message handoff.

## Live API
`https://www.girisonfoodproducts.online/api/products.php`

Expected JSON: `{ "success": true, "products": [...] }` with `id`, `product_type`, `pack_size`, `selling_price`, `mrp`, and stock fields. The app reads the API at runtime; products/prices are not hardcoded.

## Build APK on GitHub
1. Extract this ZIP.
2. Create a GitHub repository and upload **all extracted files**, including the hidden `.github` folder.
3. Open the repository's **Actions** tab. Enable Actions if prompted.
4. Choose **Build Girison Food Products APK** → **Run workflow**.
5. When complete, open the workflow run and download artifact `GirisonFoodProducts-debug-apk`. Unzip it to find `app-debug.apk`.

The workflow builds a debug APK for testing. A signed release build is required for Play Store distribution.

## Order flow note
Checkout creates an order summary and opens WhatsApp with the text prefilled. The customer reviews and sends it. This does not create a server-side order record; for that, a secure order-submission API endpoint must be implemented on the website.
