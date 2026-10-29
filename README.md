# OAuth Runway — Vercel deployment package

Static HTML app. No build command or framework is required. The live generator defaults to Gemini 3.8 Flash (`gemini-3.8-flash`).

## Deploy with Vercel CLI (recommended)

1. Install Node.js if `node` / `npm` are not available: https://nodejs.org/
2. Extract this ZIP.
3. Open Terminal in the extracted `oauth-runway-vercel` folder.
4. Run:

   ```bash
   npx vercel login
   npx vercel --prod
   ```

5. Follow the prompts to link/create the Vercel project. Vercel prints the deployed URL when deployment finishes.

## Alternative: Git-connected deployment

Create a GitHub repository, upload `index.html` and `vercel.json`, then in Vercel choose **Add New → Project**, import the repository, and deploy. Choose **Other** if a framework preset is requested; no build command is needed, and the project root is the output.

## API key and privacy notes

- The Gemini API key is not embedded in the HTML and should never be committed to GitHub or added as a Vercel environment variable for this static client-only version.
- Each person using live generation enters their own Gemini API key in the browser. The app sends it directly to Google's Gemini API in an `x-goog-api-key` request header.
- Do not use the app with confidential prompts or data. Do not tick “remember in this tab” on a shared computer; that option stores the key in the browser session storage.
- Anyone who can access the site can use the static guide library. Live generation requires their own key and available Gemini quota.

## Project contents

- `index.html` — OAuth Runway app
- `vercel.json` — security response headers
