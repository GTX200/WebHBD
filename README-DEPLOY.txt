GHZ MULTI DOWNLOADER - FIXED

1. Upload these files to the Worker project:
   - index.js
   - wrangler.toml
   - package.json

2. Cloudflare Worker Deploy command:
   npx wrangler deploy

3. The RAPIDAPI_KEY Secret must already exist with the exact name:
   RAPIDAPI_KEY

4. DO NOT use this as the deploy command:
   npx wrangler secret put RAPIDAPI_KEY --name ghz-multi-downloader

   That command only changes the secret; it does not deploy index.js.

5. After deployment, test:
   https://ghz-multi-downloader.ghzxyaa.workers.dev/api/health

   Expected JSON includes:
   "success": true
   "rapidapi_key": true

6. Download requests are now routed through /api/file instead of navigating
   directly to the provider URL.
