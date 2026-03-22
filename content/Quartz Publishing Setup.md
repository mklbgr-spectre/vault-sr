#meta #setup #publishing

# Quartz Publishing Setup

A read-only web version of this vault, built with Quartz v4 and hosted on GitHub Pages. Free, no plugins, no sync daemons.

**Live URL:** https://mklbgr-spectre.github.io/vault-sr/
**GitHub repo:** https://github.com/mklbgr-spectre/vault-sr

---

## To Publish Updates

Run this alias from any terminal:

```bash
publish-vault
```

That's it. It copies the vault, commits it, and pushes to GitHub. The site rebuilds automatically via GitHub Actions — takes about 2 minutes to go live.

---

## What the Alias Does

Defined in `~/.bashrc`:

```bash
cd ~/quartz && rm -rf content && cp -r "/mnt/wdssd/ACTIVE_TTRP/shadowrun london" content && git add content && git commit -m "update vault" && git push origin HEAD
```

In plain terms:
1. Goes to the Quartz directory
2. Deletes the old vault copy
3. Copies the current vault in fresh
4. Commits and pushes to GitHub
5. GitHub Actions picks it up and deploys

---

## Important: Keep PDFs Out of the Vault

The Shadowrun rulebooks are in the vault directory but must **not** be published — that would be distributing copyrighted material. They were physically moved out before the first push.

> [!warning] Before running `publish-vault`
> Make sure no PDF files have been added back into `/mnt/wdssd/ACTIVE_TTRP/shadowrun london/`. The copy step will include everything it finds.

---

## Local Preview (optional)

To preview the site locally before publishing:

```bash
cd ~/quartz
npx quartz build --serve
```

Then open http://localhost:8080.

> [!note] Node version
> Quartz requires Node v22. This is managed via nvm with `nvm alias default 22` already set — new shell sessions will use v22 automatically. No manual switching needed.

---

## Infrastructure Notes

| Thing | Detail |
|---|---|
| Quartz install | `~/quartz/` |
| Content folder | Physical copy of vault — not a symlink (symlinks break on GitHub's servers) |
| Deploy branch | `main` |
| Deploy workflow | `~/quartz/.github/workflows/deploy.yml` |
| GitHub account | mklbgr-spectre / mklbgr@gmail.com |
| Node version | v22 via nvm |

---

## Obsidian Compatibility

Quartz renders Obsidian-flavoured markdown correctly:
- `[[wikilinks]]` → working hyperlinks
- `> [!note]` callouts → rendered callouts
- Frontmatter tags → searchable
- Graph view and search work out of the box

The `date: 0` warnings during build are harmless — Quartz just can't sort notes by date since none have a `date:` field in their frontmatter. Everything renders fine regardless.
