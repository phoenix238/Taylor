# Taylor

Clickable prototype of a bespoke tailoring client portal. It's meant as a demo to walk through with the tailor, not a production app yet.

Open `portal/index.html` in a browser. It's a single file with no build step.

## What's in it

| Screen | What the client does |
| --- | --- |
| **Portal** | See the current commission's progress (measured → cloth cut → baste → forward fitting → finishing → collection), the next fitting, their measurements and saved designs |
| **1 · Measure** | Enter height and weight, then take a front and side photo (or upload them). The scan maps 10 measurements plus posture notes, and suggests a size, drop and fit |
| **2 · Design** | Build the suit on a live drawing: 9 cloths or any custom colour, cut (SB 1/2/3, DB 6×2), silhouette, lapel style and width, pockets, trousers, buttons, lining, vents, tie and monogram. The price updates as options change |
| **3 · Review** | A cutting ticket with the full spec and measurements. Book a fitting slot |

## What is simulated

- **Body scan.** The flow assumes a measurement app or service supplies the numbers; which one is decided later. Until then the measurements are estimated from height and weight.
- **Client account, orders, bookings.** Everything is example data or kept in this browser's `localStorage`. Nothing is sent anywhere.
- **Prices, cloths and timings** are placeholders to replace with the tailor's real numbers. Set the currency with `BRAND.currency` at the top of the script.

## Putting it on the Squarespace site

Squarespace can't host an app like this itself. The usual setup:

1. Host `portal/index.html` somewhere static, such as GitHub Pages, Vercel or Netlify.
2. On Squarespace, either add a **Client portal** navigation link to that URL, or embed it in a page with a Code Block: `<iframe src="https://…/portal/" style="width:100%;height:100vh;border:0"></iframe>`.
3. For real logins, saved scans and orders, add a backend (for example Supabase or Firebase). Squarespace Member Areas can gate the page, but they don't store per-client data.
