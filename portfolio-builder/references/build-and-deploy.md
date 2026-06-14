# Build and deploy

Technical guidance for assembling the codebase and getting it live. Read before the assembly step.

## Contents
- [Choosing the build](#choosing-the-build)
- [Content as data](#content-as-data)
- [Styling approach](#styling-approach)
- [Multi-page routing and host rewrites](#multi-page-routing-and-host-rewrites)
- [The quality floor](#the-quality-floor)
- [Verify before handoff](#verify-before-handoff)
- [Hosting options](#hosting-options)
- [Deploy gotchas](#deploy-gotchas)

---

## Choosing the build

Default the technical choices for non-technical people. Don't ask them to pick; decide and proceed.

- **Default (non-technical or unsure):** a single self-contained `index.html` with HTML, CSS, and a little JS in one file. It is the most portable option and needs no build step, so it deploys by drag-and-drop. This is the right answer unless there's a reason to deviate.
- **Refreshing an existing site:** match their framework and structure exactly and return drop-in files. Don't switch their stack unless something is broken; the priority is that it slots back into their hosting with no config change.
- **Technical person from scratch:** their preference wins. React or Vite, Next, Astro, and plain HTML are all fine.

When a person zipped an existing project, watch for missing config files (for example a Tailwind or PostCSS config that wasn't included). If you can't be sure their build pipeline is intact, prefer self-contained CSS over a utility framework so the result builds and deploys regardless. Note this trade-off to them.

## Content as data

Put every section's content in clearly labelled arrays or objects at the top of the main file, separated from markup. The person should be able to update copy, add a project, or add a job by editing data, never touching layout. Document the shape in a comment or the README. Example outcome: "add one object to the `PROJECTS` array and a card renders itself."

This is the single highest-leverage thing for the site's longevity. Most people will never touch the markup, but they will want to add a project next year.

## Styling approach

- Self-contained CSS (one stylesheet, CSS variables for the palette and fonts) is the most robust choice and gives full control over a bespoke design. It builds anywhere.
- Define the palette and type once as CSS variables; reference them everywhere.
- Load fonts via a `<link>` in the HTML head (with preconnect), not a CSS `@import`, to avoid build-order issues.
- A utility framework is fine when the existing project already uses it correctly; match what's there.

## Multi-page routing and host rewrites

When the site grows beyond one page (a `/tools`, `/blog`, or case-study route):

- For a simple single-page app, a tiny dependency-free router (read `window.location.pathname`, `history.pushState`, listen for `popstate`) avoids adding libraries and version risk.
- Add the host rewrite so deep links and refreshes resolve to the app instead of returning a 404. This step is easy to forget and breaks refreshes when missed.
  - **Firebase:** `firebase.json` with `"rewrites": [{ "source": "**", "destination": "/index.html" }]`.
  - **Netlify:** a `_redirects` file containing `/*  /index.html  200`.
  - **Vercel:** handled for single-page frameworks; for custom setups add a rewrite in `vercel.json`.
  - **GitHub Pages:** no server rewrites, so use hash routing or a `404.html` fallback.
- Build the new area as a system (content-as-data again) with a strong empty state if it has nothing in it yet.

## The quality floor

Build these in without announcing them:

- Responsive down to a narrow mobile viewport (test the nav, grids, and any side-by-side hero).
- Visible keyboard focus on interactive elements.
- `prefers-reduced-motion` respected, so disable scroll-tracking and non-essential animation.
- Real `<title>`, meta description, and favicon; preserve the person's existing ones.
- Semantic structure and adequate colour contrast (check accent-on-background and text-on-dark).
- No reliance on browser storage in sandboxed preview environments.

## Verify before handoff

Before delivering, confirm the code at least parses or transforms cleanly (for example a quick esbuild or babel transform for JSX, or open the HTML). Re-run any content rule the person set (for example grep for characters they asked to avoid, such as em dashes). Catching a broken build now is far cheaper than after they try to deploy.

## Hosting options

For a static or single-page portfolio, all of these have free tiers. For a non-technical person, default to the drag-and-drop options and walk them through the clicks:

- **Netlify Drop or Vercel:** drag-and-drop or git-connected; instant URL; easiest for non-technical people. This is the default.
- **GitHub Pages:** free, good if they already use GitHub.
- **Cloudflare Pages:** fast, free.
- **Firebase Hosting:** free Spark tier, HTTPS, custom domains; slightly more setup via the CLI, good if they want room to add dynamic features later.

The built site is the same artifact; only the upload step differs. Give the specific steps for the host they actually use.

## Deploy gotchas

- A freshly unzipped folder does **not** carry an existing project's deploy link or login. If the person already hosts the site, the smoothest path is to drop the updated files into their existing project folder and run their normal build and deploy, rather than deploying the new folder cold.
- First-time CLI deploys (for example Firebase) need the CLI installed, a login, and the target project selected.
- Confirm what their current deploy command actually is before promising the new files "just slot in."
