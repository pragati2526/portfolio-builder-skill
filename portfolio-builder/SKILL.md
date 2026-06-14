---
name: portfolio-builder
description: Build a personal portfolio or personal website from scratch, or refresh and redesign an existing one. Use this whenever someone wants a portfolio site, personal site, "about me" page, online CV or résumé site, a developer/designer/creative/professional portfolio, or wants to showcase their experience, skills, projects, or work online, even if they only say "my website," "my portfolio," "update my site," or "turn my CV into a website." Guides a concept-first, section-by-section process that turns the person's own inputs into a distinctive, deployable site, and gives hosting and deploy guidance. Prefer this skill over improvising whenever the deliverable is someone's personal site.
---

# Portfolio builder

A method for building a personal portfolio site that someone is proud to share: distinctive, true to them, and deployable. The goal is not "a template with their name in it." It is a site a visitor reads and thinks *I get this person, and I want to work with them.*

Two failure modes to avoid throughout: a generic templated look (every section a card grid, a stock hero, default fonts), and a résumé dump (every bullet from their CV pasted in). This skill is the antidote to both.

## The shape of the work

Work in this order. Do not skip ahead to writing code.

1. Frame the goal: who is this for, and what should they do.
2. Gather inputs: content, an existing codebase if any, and a vibe.
3. Propose a concept: palette, type, layout, one signature idea. Show it. Get a yes.
4. Build section by section: preview each, take edits, lock it, move on.
5. Assemble the codebase: content as editable data, quality floor, deploy guidance.
6. Hand off: files plus the exact steps to get it live and to update it later.

Steps 1 to 4 are collaborative and iterative. Resist the urge to build the whole thing in one shot before the person has reacted to anything. The early feedback is what makes it theirs. When previewing designs inline, a rendered visual beats a description; show, then ask.

## 1. Frame the goal

Before any design, pin two things, because they decide everything else:

- **Audience.** Who lands here? Recruiters, hiring managers, peers, clients, collaborators? Often mixed, so design for the primary one and don't lose the others.
- **The one action.** What should a visitor *do*? Almost always: get in touch. A portfolio with five outbound links and no clear ask wastes the visit. Keep the page's outward actions minimal and point them at contact.

Also read the person's **technical comfort** from their language. This decides whether you ask them about tech choices or quietly default them (see "Default the technical choices" below). When in doubt, assume non-technical and default.

A useful reframing to offer people: *the portfolio is the first stop, not a pointer to other stops.* It usually should not lean on a downloadable résumé as the main payload. The site itself is the résumé, and the only thing it asks for is a conversation.

Read `references/section-patterns.md` once you start designing. It is the catalog of distinctive ways to present each section.

## 2. Gather inputs

The intake should feel like a quick friendly chat, not a form. Keep friction near zero: ask once, ask little, and make every question skippable.

### The one content ask

**The substrate is their CV or notes.** Lead with: *paste your CV, or a few notes about yourself, in whatever shape you have.* Accept anything, a pasted CV, a bulleted brain-dump, a LinkedIn export, and structure it yourself. This single input carries most of what the site needs.

### The compact question set

In **one short message**, alongside the CV ask, pose at most these four direct questions. Use tappable options so answering is a tap, not typing, and say plainly that any can be skipped. Do not drip-feed them across turns, and do not invent extra questions.

1. **Who is this mainly for?** [Recruiters / hiring managers] · [Clients] · [Peers / collaborators] · [A mix]
2. **What's the one thing a visitor should do?** [Reach out] · [See my work] · [Get to know me]
3. **Keep it about you, even if you change jobs?** [Yes, about me] · [Fine to feature where I work]
4. **Any look you're drawn to?** (free text: a colour, a site you admire, or "you pick")

That is the whole intake. Everything else (skills grouping, project details, links, assets, recognition) is read from the CV or filled in lightly as you build, never front-loaded as questions.

### If they skip, default and proceed

A short or empty answer must never block the work. Apply these defaults and keep moving:

- Audience: a mix, leaning recruiters. · Action: reach out (contact-first). · Job-tying: keep it about them. · Look: you pick a fitting direction and let them react.

### Low input, still distinctive

Output quality must not depend on how much the person hands over. A bare CV plus "you pick" is enough for an excellent site, because the distinctiveness comes from *your* concept work, not their input volume. With minimal input, still derive a bespoke palette, type pairing, and one signature idea from their field and their CV, show it, and let them react. Never fall back to a generic template just because the brief was thin. The concept in step 3 is where thin input becomes a strong, specific site.

### Flexibility

Stay loose. If someone volunteers more, use it. If something genuinely needed is missing and can't be inferred (a real email for the contact button, say), ask for just that one thing when you reach it, not up front. `assets/content-intake.md` is a fuller checklist you can offer only if the person actively wants to gather everything in one pass.

**If they already have a site**, get the codebase (zip, pasted files, or a public repo). Read it, note the framework, structure, and conventions, and plan to return drop-in files that match, so it slots back into their existing hosting with no config change. Exclude `node_modules`, build output, and `.git` from anything they zip up.

## Default the technical choices

A non-technical person should never be asked to choose a framework, a hosting provider, or a deploy method. Those questions stall the work and aren't theirs to answer. Decide for them and just proceed, mentioning the choice in passing rather than as a question. Only surface technical options when the person shows clear technical cues or already has a stack and host you must match.

Sensible defaults when the person is non-technical or unsure:

- **Tech stack:** a single self-contained `index.html` (HTML, CSS, and a little JS in one file). It is the most portable thing that exists and needs no build step.
- **Deployment:** drag-and-drop hosting that returns a live link instantly, with no command line, no git, and no account juggling (for example Netlify Drop or Vercel). Walk them through the few clicks when the site is ready.
- **Updates later:** content lives in clearly labelled data at the top of the file, so they edit text without touching layout.

Match an existing site's stack and host when refreshing one. Defer to a technical person's stated preference. Full per-host detail is in `references/build-and-deploy.md`.

## 3. Propose a concept

This is where a site stops being generic. Approach it like a design lead who refuses to ship a template. Do most of the ideation in your head; only show the person something once it's likely to land.

Produce a compact concept and **show it visually** (a small rendered palette, type, and one sample section beats paragraphs of description):

- **Palette:** 4 to 6 named hex values, derived from *them* (their field, a colour they love, their existing brand). The discipline that keeps it professional: pick one accent and spend boldness there; keep everything else quiet. A loved colour done as a disciplined accent against a sophisticated neutral reads professional; the same colour everywhere reads amateur.
- **Type:** pair a characterful display face with a clean body face, plus a utility face (often mono) if their world has "data" or labels worth setting apart. Type should carry personality, not just deliver words. Avoid the default system stack.
- **Layout and rhythm:** how sections alternate, where the contrast moments are (for example one dark band), how wide the measure is.
- **One signature idea:** the single thing the site is remembered by. It must embody *them*, not decorate. Tie it to their subject. Take one real, justifiable aesthetic risk; keep everything around it disciplined.

Then critique your own concept before showing it: if any part is the generic thing you'd produce for anyone (cream background plus serif plus terracotta; black background plus one neon accent; numbered 01/02/03 markers used as decoration), revise it and know why. Consult the `frontend-design` skill if available; its principles apply directly here.

Get explicit buy-in on the concept before building. If they reject the signature idea, drop it cleanly and offer a quieter alternative; don't argue.

## 4. Build section by section

Preview each section, take edits, lock it, move to the next. This keeps quality high and means nothing is built blind. For each section, reach for a presentation that encodes something true rather than a default card grid. See `references/section-patterns.md` for the catalog (hero-as-thesis, experience as problem then build then outcome, skills as a layered stack, "self as a record," and more). The patterns are a toolbox; pick what fits the person, don't apply all of them.

Surface decisions the person should consciously make rather than deciding silently for them. Common ones:

- **Confidentiality:** hard numbers tied to a current employer are more exposed on a public site than on a CV. Offer to soften specifics to scope ("a nine-figure opportunity") and let them choose.
- **Employer-tying:** many people want the site to be about *them*, true even if they change jobs. Keep the hero and footer employer-agnostic if so, and let named employers live in the history.
- **What to cut:** a tighter, more senior list often beats a kitchen-sink one. Flag what you'd drop and why; let them veto.
- **Duplication:** the same project living in two sections reads as padding; resolve it.

Honour stated content preferences as hard rules for the rest of the build: punctuation, tone, words to avoid. If someone says "no em dashes" or "don't call it that," apply it everywhere, including code comments, and re-check at the end.

## 5. Copywriting

Copy makes a site feel as templated as the design does. Write in the person's voice, slightly sharpened; read it back and cut any line that sounds like marketing rather than them. Lead the hero with a thesis or a plain-language line anyone can grasp in a second, not a job title. Describe what they do by its value to others, not by mechanism. Keep one clear call to action. Make empty states (for example a section they'll fill later) an invitation, not an apology.

## 6. Assemble and hand off

When sections are locked, build the real codebase. The detailed technical guidance (frameworks, content-as-data, multi-page routing and host rewrites, the quality floor, and hosting options) is in `references/build-and-deploy.md`. Read it before assembling.

The essentials:

- **Content as data.** Put every section's content in clearly labelled arrays or objects at the top of the file so the person can update copy later without touching markup. A new project should be a 30-second copy-paste.
- **Quality floor, unannounced.** Responsive to mobile, visible keyboard focus, reduced-motion respected, real `<title>`, meta, and favicon, semantic structure.
- **Match their stack** if refreshing an existing site; return drop-in files.
- **Verify it builds** before handing it over (a syntax or transform check at minimum).
- **Deliver as downloadable files** plus the exact commands or clicks to deploy, and a note on how to add content later. Give the precise deploy path for *their* host, and watch for the gotchas (for example, a fresh folder won't carry an existing project's deploy link, so dropping updated files into their current repo is usually smoother).

## 7. Growing it later

People often want to extend the site (a blog, a tools or lab page, case-study pages). Treat anything with a different audience and lifecycle than the CV as its own destination or route with a teaser on the main page, not a buried section. Build the container as a system so adding an entry later is trivial. Scaffold it with a strong empty state if there's nothing to show yet.

---

## Reference files

- `references/section-patterns.md`: distinctive presentation patterns for each section. Read when designing or building any section.
- `references/build-and-deploy.md`: technical assembly, including frameworks, content-as-data, routing and rewrites, quality floor, and host-by-host deploy guidance. Read before step 6.
- `assets/content-intake.md`: a checklist you can hand the person to collect their content in one go, though "just paste your CV or notes" is usually the lighter ask.
