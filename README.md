# Pixelcave Skills

Agent skills for Pixelcave projects. Install them into your AI coding agent (Claude Code, Cursor, Codex, and others) so it knows how to use our products directly from your editor.

This repo is a catalog. Each top-level folder under `[skills/](skills/)` is one self-contained skill with its own `SKILL.md`, so you can install just the ones you need.

## Available skills


| Skill                                  | What it does                                                                                                                                                                                                                              |
| -------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `[codedvisuals](skills/codedvisuals/)` | Add [CodedVisuals](https://codedvisuals.com) marketing visuals (charts, heroes, bento grids, dashboards, chat, code editors, and more) to a React marketing or landing page. Covers picking a visual, installing it, and using its props. |


More skills for other Pixelcave projects will be added here over time.

## Install

These skills are distributed through `[skills](https://www.npmjs.com/package/skills)`, the open agent skills CLI. No global install needed, run it with `npx`.

Install everything in this repo:

```bash
npx skills add pixelcave/skills
```

Install a single skill (recommended, see [Installing a subset](#installing-a-subset)):

```bash
npx skills add pixelcave/skills --skill codedvisuals
```

By default the CLI installs into the current project. Add `-g` to install into your user directory so the skill is available across all projects:

```bash
npx skills add pixelcave/skills --skill codedvisuals -g
```

### Installing a subset

You do not have to install the whole repo. The `--skill` flag (repeatable) targets skills by folder name:

```bash
# One skill
npx skills add pixelcave/skills --skill codedvisuals

# Several skills
npx skills add pixelcave/skills --skill codedvisuals --skill some-other-skill

# Everything, no prompt
npx skills add pixelcave/skills --skill '*'
```

Run without `--skill` to get an interactive picker, or preview what is available first:

```bash
npx skills add pixelcave/skills --list
```

### Target a specific agent

By default the CLI detects the agents in your project. Scope the install with `-a`:

```bash
npx skills add pixelcave/skills --skill codedvisuals -a claude-code
```

### Other commands

```bash
npx skills list              # show installed skills
npx skills update            # update installed skills to the latest version
npx skills remove codedvisuals   # uninstall a skill
```

See the `[skills` CLI docs]([https://github.com/vercel-labs/skills](https://github.com/vercel-labs/skills)) for the full command reference.

## Using the CodedVisuals skill

The `codedvisuals` skill teaches your agent the full visual catalog, each component's props and defaults, and how to install a visual. Once installed, just ask your agent for a visual, for example "add visuals to all my feature blocks" or "drop in a line chart visual", and it will pick the right ones and wire them up automatically.

Installing a visual's source pulls from the private CodedVisuals shadcn registry, which requires an active license and a personal registry token. The skill itself (the catalog and docs) is free and public, the component source is licensed. Get a license at [codedvisuals.com/pricing](https://codedvisuals.com/pricing) and set up your token from your account settings.

## Repo structure

```
skills/
  codedvisuals/
    SKILL.md           # router: catalog + how to install and use a visual
    manual-setup.md    # setup for projects without shadcn/ui
    visuals/           # one reference file per visual, with props and examples
      charts/line.md
      sections/hero.md
      ...
```

Each skill lives in its own folder with a `SKILL.md` at its root, the layout the `skills` CLI expects, so skills stay independently installable as the catalog grows.

## License

The skill content in this repo is provided as-is for use with Pixelcave products. CodedVisuals component source is licensed separately, see [codedvisuals.com](https://codedvisuals.com).

## Support

For support, please get in touch at [pixelcave.com/contact](https://pixelcave.com/contact).