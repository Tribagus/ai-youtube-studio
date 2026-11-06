# AI YouTube Automation Studio

Static web app for Android and desktop. It sends the selected video to Gemini API for video understanding and metadata generation, then uploads the original video to YouTube using Google OAuth and YouTube Data API resumable upload.

## Hosting
Upload `index.html` to a GitHub repository and enable GitHub Pages (Settings → Pages → Deploy from branch → main → /(root)). HTTPS is required for Google OAuth. Can also be hosted on Cloudflare Pages.

## Setup
### Gemini
1. Create a Gemini API key in Google AI Studio.
2. Use a model available to your account's free tier. This prototype uses `gemini-2.0-flash`; if unavailable, change `model` in index.html to a currently available video-capable model.
3. Free tier has rate/usage limits and availability can change. The key is entered in the browser at runtime and held only in page memory; do not share it or publish it.

### YouTube OAuth
1. Create a Google Cloud project and enable YouTube Data API v3.
2. Configure OAuth consent screen. Add your own channel account as a test user while app is in Testing.
3. Create OAuth Client ID → Web application.
4. Add the exact HTTPS GitHub Pages URL under Authorized JavaScript origins.
5. Paste Client ID into app and connect YouTube. No client secret belongs in browser code.

## Behavior and safety
- Once the user checks the consent checkbox and clicks Start, AI analyzes the video and uploads automatically using the selected privacy and audience settings.
- Default privacy is Public. Change to Unlisted/Private before starting if desired.
- Use only videos you own or have permission to publish. AI metadata should be reviewed periodically for accuracy.
- Gemini processing uploads the source video to Google's API. Review applicable privacy and retention terms before using sensitive content.
- This prototype uploads the original video; it does not edit, trim, generate a thumbnail, schedule, or guarantee SEO ranking.
- Browser must stay open while upload runs. YouTube API quota and OAuth restrictions apply. The free tier is not unlimited.
