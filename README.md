# Portfolio Builder (a Claude skill)

A Claude skill that builds a personal portfolio website that someone is proud to share: distinctive, true to them, and ready to deploy. It runs a concept-first, section-by-section process that turns a CV and a couple of answers into a site that does not look like a template.

It works for any profession and any stack, from scratch or refreshing an existing site, and it defaults the technical choices so non-technical people never have to pick a framework or a host.

## What it does

- Frames the goal (who the site is for, what a visitor should do)
- Takes a CV or rough notes plus a tiny, skippable set of questions
- Proposes a real design concept (palette, type, one signature idea), then builds section by section
- Produces a deployable codebase with content kept as easy-to-edit data
- Gives the exact steps to get it live and to update it later

## Install

A skill is just a folder with a `SKILL.md` file. Pick the surface you use:

**Claude.ai** (Pro, Max, Team, or Enterprise with code execution enabled)
1. Download `portfolio-builder.zip` from this repo (or zip the `portfolio-builder/` folder yourself).
2. In Claude, go to Settings > Features and upload the zip.
3. Start a chat and say something like "help me build my portfolio site."

**Claude Code**
```
git clone https://github.com/<your-username>/portfolio-builder-skill.git
cp -r portfolio-builder-skill/portfolio-builder ~/.claude/skills/portfolio-builder
```
Restart Claude Code, then just ask it to build a portfolio.

**Claude API**
Upload the skill through the Skills API. See the docs below.

Official instructions: https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview

## How to use it

Once installed, you do not need to invoke anything special. Just ask Claude to build or refresh a portfolio site, paste your CV or notes, and answer the few short questions (or skip them). The skill takes it from there.

## What's inside

```
portfolio-builder/
  SKILL.md                       the workflow
  references/
    section-patterns.md          distinctive ways to present each section
    build-and-deploy.md          stacks, routing, hosting, deploy gotchas
  assets/
    content-intake.md            an optional content checklist
```

## A note on trust

Skills run with access to your Claude session, so people are rightly advised to install only skills from sources they trust. This one contains plain Markdown instructions and no scripts. Read `portfolio-builder/SKILL.md` before installing, as you should with any skill.

## License

MIT. Use it, change it, share it. See `LICENSE`.

Built by Pragati Singh.
