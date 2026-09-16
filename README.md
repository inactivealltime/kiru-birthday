# Kiru Birthday · a private little story

A static, mobile-first interactive birthday experience for Kirat. It has no build step and can be hosted on GitHub Pages, Netlify, Vercel, or any static HTTPS host.

## Personalise it

Edit **`config.js` only** for the main personal content:

- `herName`, `myName`, `birthday`
- `relationshipStart` (ISO date/time)
- `messages`, `letter`, and `finalMessage`
- `gallery` photo paths, alt text, and captions
- `photoTimeline` years, dates, captions, and image paths
- `songUrl`

Keep text inside quotes. Use `\n` for a new paragraph. Replace `[MY NAME]` and every bracketed placeholder before sharing.

## Add photos

Create an `assets` folder in the repository, upload files such as `gallery-01.jpg`, then set values in `config.js`:

```js
{ src: 'assets/gallery-01.jpg', alt: 'Our gallery day', caption: 'A caption only we understand' }
```

Use compressed JPG/WebP images, ideally under 500 KB each. Empty `src` values intentionally show graceful placeholders.

## Add music

Only use music you created, licensed, or have permission to share. Upload an MP3 to `assets/` and set:

```js
songUrl: 'assets/our-song.mp3'
```

The music begins only after the opening button is tapped. The floating control can pause or resume it. If no song is configured, the site still works normally.

## Deploy on GitHub Pages

1. Open **Settings → Pages** in this repository.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Choose `main` and `/ (root)`, then Save.
4. GitHub will provide a public HTTPS address, usually:
   `https://inactivealltime.github.io/kiru-birthday/`
5. Wait for the Pages deployment to finish, open the URL once, and scan the QR shown on the final screen. The QR is generated from the current URL automatically.

The QR image uses a small external QR image service. If offline/self-contained QR generation is required, replace that line in `app.js` with a locally hosted QR library.

## Browser notes

The experience is a single-page app with cinematic screen transitions, live relationship timers, typewriter messages, touch-friendly horizontal gallery swiping, zoomable photos, graceful missing-photo states, lazy-loaded images, and responsive layouts for Safari, Chrome, Edge, Android, and iPhone.
