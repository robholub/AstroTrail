AstroTrail Pro 🌌

AstroTrail Pro is a lightweight, offline-capable Progressive Web App (PWA) designed for astrophotographers. It calculates the absolute maximum shutter speed you can use before stars begin to trail in your photos, preventing blurry night sky images.

It supports both the standard Rule of 500 and the highly precise NPF Rule, which accounts for your specific camera's pixel density and the declination of the stars you are photographing.

✨ Features

Advanced NPF Rule: Calculates exact pixel pitch using sensor size and megapixels to provide tack-sharp exposure limits.

Declination Slider: Adjusts exposure allowances based on where the camera is pointed (Equator vs. Poles).

Gear Profiles: Save your favorite camera and lens combinations to local storage for instant loading in the dark.

True Night Vision Mode: Toggles the UI to pure black and deep red to protect your eyes' dark adaptation while out in the field.

100% Offline Capable: Built with a Service Worker, allowing the app to function perfectly in remote locations without cell service.

🛠️ Architecture

To keep the project extremely simple and easy to deploy directly from a mobile phone, this app uses a Single-File Architecture rather than a traditional Node/Vite build pipeline.

Frontend: React 18 & Babel (imported directly via CDN).

Styling: Tailwind CSS (imported directly via CDN).

Icons: Inline SVG components.

State Management: React useState, useMemo, and browser localStorage.

Deployment: Hosted on Vercel and packaged for the Google Play Store using PWABuilder.

📂 Project Structure

index.html: Contains the entirety of the application logic, UI, and React components.

manifest.json: The Web App Manifest required for PWA installation and Android theming.

sw.js: The Service Worker that caches assets for offline use.

icon.png: The 512x512 app logo used by the Android operating system.

.well-known/assetlinks.json: Verifies website ownership to Android, allowing the app to run as a Trusted Web Activity (TWA) without a browser address bar.

🚀 Deployment Guide

Because there is no build step, deploying this app is instantaneous:

Fork or clone this repository.

Link your repository to Vercel and click Deploy (no build commands necessary).

Ensure you have your icon.png uploaded to the root directory.

Run your Vercel URL through PWABuilder.com to generate the Android App Bundle (.aab) for the Google Play Store.

💰 A Note on the Paywall

Currently, the codebase contains a Simulated Paywall for the NPF Rule feature. It utilizes localStorage to check for a astroProStatus flag.

If you are packaging this for the official Google Play Store to process real transactions, you must replace the simulatePurchase() function in index.html with the official Digital Goods API and Payment Request API to verify purchases securely against the user's Google Play account.
