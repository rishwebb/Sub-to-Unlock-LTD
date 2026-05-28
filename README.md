# Sub4Unlock Premium

A modern, single-file link locker built with pure HTML, CSS, and JavaScript.
Creators can generate task-based unlock links, and users must complete social steps before the destination is unlocked.

[![Built with HTML](https://img.shields.io/badge/Built%20With-HTML-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![Built with CSS](https://img.shields.io/badge/Built%20With-CSS-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![Built with JS](https://img.shields.io/badge/Built%20With-JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=111827)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Single File App](https://img.shields.io/badge/App%20Type-Single%20File-0F766E?style=for-the-badge)](#project-structure)

## Highlights

- Clean premium UI with responsive layout and motion polish.
- One-file architecture (`index.html`) for easy hosting.
- Per-link progress memory using `localStorage` (same link stays completed on revisit).
- Different generated links require fresh completion.
- Per-task pause/resume controls in creator mode to include only selected steps in generated links.
- On return from a task, buttons show a visual "Verifying task..." spinner for a randomized 2-4 seconds before marking done.
- Locked YouTube channel step is fixed to `https://www.youtube.com/@Bingxxo`.
- Locked Instagram follow step is fixed to `https://www.instagram.com/erro_rcodee/`.
- URL sanitization for task and destination links (`http/https` only).
- Safe decode and storage handling to reduce runtime errors.

## Project Structure

```text
Sub4Unlock/
├── index.html   # Full app: UI + logic + styles
└── README.md
```

## How It Works

1. Creator opens the page without query params.
2. Creator fills the fields and generates a share link.
3. Generated link includes encoded task data and destination.
4. User opens that link and completes visible steps.
5. Unlock button activates once required steps are completed.

## Local Run

Because this is static, you can run it directly or with any local static server.

### Option 1: Open directly

Open `index.html` in your browser.

### Option 2: Serve locally (recommended)

```bash
python3 -m http.server 8080
```

Then open:

```text
http://localhost:8080
```

## Deploy

You can host this on any static host:

- GitHub Pages
- Netlify
- Vercel (static)
- Cloudflare Pages
- Any cPanel/static web host

No backend is required for current behavior.

## Configuration

### Locked YouTube channel URL

Update this constant in `index.html`:

```js
const LOCKED_YT_CHANNEL_URL = "https://www.youtube.com/@Bingxxo";
```

### Tasks currently in flow

- Subscribe Channel (locked channel URL)
- Follow on Instagram (locked profile URL)
- Like YouTube Video
- Like Instagram Reel

Any task can be paused from creator mode; paused tasks are excluded from the generated link.

## Security Notes

This project is frontend-only. That means:

- It is suitable as a friction layer.
- It is not strong security for secret content.
- Advanced users can inspect or manipulate client-side code.

For real enforcement, use a backend validation flow.

## Pre-Host Checklist

1. Confirm all links are valid `https://` URLs.
2. Test one generated link twice: first open must require completion, second open (same browser) should stay completed.
3. Test a different generated link: it should require completion again.
4. Verify mobile and desktop rendering.

## Credits

Created by Rishav.
