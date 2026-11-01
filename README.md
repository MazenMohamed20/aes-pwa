# AES Archive PWA wrapper

This static site gives the AES Streamlit Cloud app its own installable web-app name and icon.

## Contents
- `index.html`: full-screen wrapper for `https://aes-archive.streamlit.app/`
- `manifest.webmanifest`: app name, short name, and PWA icon declarations
- `icons/aes.svg`: scalable vector source for the AES mark
- `icons/aes-192.png`, `icons/aes-512.png`: high-resolution PNG fallbacks rendered from the SVG
- `apple-touch-icon.png`, `favicon.png`: browser/mobile icons
- `sw.js`: minimal service worker registration

## Deploy using GitHub Pages
1. Create a **new** GitHub repository, e.g. `aes-pwa` (do not replace the existing AES repository).
2. Upload all files and the `icons` folder from this package to the repository root.
3. In the new repository, open **Settings → Pages**.
4. Under Build and deployment, choose **Deploy from a branch**, branch `main`, folder `/ (root)`, then Save.
5. Wait for GitHub Pages to publish. The public URL will look like `https://YOUR-USERNAME.github.io/aes-pwa/`.
6. Open that new URL in Android Chrome. Use **Install app** or **Add to Home screen**.
7. Remove the old Streamlit shortcut first; it will not update its icon/name retroactively.

## Important
- This wrapper does not modify the existing Streamlit code or data.
- The Streamlit app is embedded in an iframe using Streamlit's `embed=true` option.
- Test sign-in, file uploads/downloads, and all key AES workflows before relying on the wrapper. If any workflow fails inside the iframe, use a standalone PWA frontend/proxy approach instead.
