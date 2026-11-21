# NutriScan Frontend

Web app for NutriScan, an AI-powered nutrition tracker. Take a photo of your food, get its calories and macros, log meals, and track your progress against your health goals.

Built with plain HTML, CSS and JavaScript. No build step.

## Pages

| Page | Purpose |
|---|---|
| `index.html` | Login |
| `register.html` | Create an account |
| `userPreference.html` | Set up your health profile and goals |
| `Dashboard.html` | Today's calories, macros and meals |
| `Scanner.html` | Identify food from a photo and log it |
| `History.html` | Past meals |
| `Stats.html` | Charts and analytics |
| `profile.html` | Your profile and BMI |
| `About.html` | About the app |

## How it connects to the backend

The backend runs on Zoho Catalyst AppSail (see the `nutriscan-backend` repo). The browser never calls it directly. `vercel.json` forwards API paths such as `/auth/login` to the backend, so everything is same-origin and no CORS setup is needed.

`config.js` sets the API base URL. Keep it empty when deployed on Vercel:

```js
window.NUTRISCAN_API_BASE_URL = "";
```

## Run locally

1. Start the backend on `http://localhost:8080`.
2. Set `config.js` to:
   ```js
   window.NUTRISCAN_API_BASE_URL = "http://localhost:8080";
   ```
3. Open `index.html` with a local server (for example the IntelliJ preview or `npx serve`).

Set `config.js` back to `""` before you push.

## Deploy on Vercel

1. Push this repo to GitHub.
2. In Vercel, choose **Add New → Project** and import the repo.
3. Set **Framework Preset** to **Other**. Leave the build command and output directory empty.
4. Deploy. Later pushes to `main` redeploy automatically.

If the backend URL changes, update the destination URLs in `vercel.json` and push.
