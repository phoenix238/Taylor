# Taylor

Clickable prototype of a bespoke tailoring client portal. It's meant as a demo to walk through with the tailor, not a production app yet.

Open `portal/index.html` in a browser. It's a single file with no build step.

## What's in it

| Screen | What the client does |
| --- | --- |
| **1 · Consult** | A guided consultation, one question per screen: occasion, season, setting, how you want to feel, style, colour, boldness, fit, what the cut should do for you, how often you'll wear it, budget, timing and reference photos. The tailor replies to each answer, and a calico toile on a 3D stand changes shape as you go. It ends in **your edit**: three suits (our pick, a safer or different choice, and a brave one), each with the reasons it suits your brief, what to wear it with, and whether it fits your budget. You can nudge the edit (more formal, more relaxed, bolder, quieter, different colours) or try any suit on |
| **Portal** | See the current commission's progress (measured → cloth cut → baste → forward fitting → finishing → collection), the next fitting, their measurements and saved designs |
| **2 · Measure** | Enter height and weight, then take a front and side photo (or upload them). The scan maps 10 measurements plus posture notes, and suggests a size, drop and fit |
| **3 · Design** | Two paths. **Build it here:** a 3D mannequin you can turn (front, side, back, detail) wearing woven cloth. Choose from 9 cloths or any custom colour, cut (SB 1/2/3, DB 6×2), silhouette (slim to relaxed), length, lapel style and width, pockets, pleats and leg width, buttons, lining, vents, tie and monogram. One-tap starting looks include a soft, wide cut. **Bring your idea:** upload reference photos, note what you like about each, and describe it for the tailor |
| **4 · Review** | A cutting ticket with the occasion, the consultation brief, the full spec, reference photos and measurements. Book a fitting slot |

## What is simulated

- **Body scan.** The flow assumes a measurement app or service supplies the numbers; which one is decided later. Until then the measurements are estimated from height and weight.
- **3D model.** The suit is generated in the browser with three.js (loaded from jsDelivr): procedural woven-cloth textures, soft drape, rolled edges, a turntable in a fixed studio light. It looks like a product render, not a photo. Photoreal garments would need 3D assets made by an artist.
- **The edit** is chosen by rules written into the page (15 looks, scored against the answers). The looks, reasons and prices should be rewritten with the tailor so they're his advice.
- **Reference photos** stay in the browser for the session. A live version would upload them to the tailor.
- **Client account, orders, bookings.** Everything is example data or kept in this browser's `localStorage`. Nothing is sent anywhere.
- **Prices, cloths and timings** are placeholders to replace with the tailor's real numbers. Set the currency with `BRAND.currency` at the top of the script.

## Putting it on the Squarespace site

Squarespace can't host an app like this itself. The usual setup:

1. Host `portal/index.html` somewhere static, such as GitHub Pages, Vercel or Netlify.
2. On Squarespace, either add a **Client portal** navigation link to that URL, or embed it in a page with a Code Block: `<iframe src="https://…/portal/" style="width:100%;height:100vh;border:0"></iframe>`.
3. For real logins, saved scans and orders, add a backend (for example Supabase or Firebase). Squarespace Member Areas can gate the page, but they don't store per-client data.
