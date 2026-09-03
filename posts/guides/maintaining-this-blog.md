# Maintaining this blog in 30 seconds

No CMS. No terminal gymnastics.

## Add a post

```bash
# 1. pick a topic folder (or make one) and create the file
posts/notes/my-new-post.md

# 2. (optional) add images mirroring the folder
images/notes/my-new-post/cover.png
```

Reference images root-relative:

```md
![Cover](images/notes/my-new-post/cover.png)
```

Files next to your post work too — `./cover.png` resolves against the post's own folder. Legacy `../images/...` paths are rewritten automatically.

## Register it

Add one object to `posts.json`:

```json
{
  "slug": "my-new-post",
  "title": "My New Post",
  "folder": "notes",
  "file": "my-new-post.md",
  "date": "2026-09-10",
  "excerpt": "One-line teaser for the explorer"
}
```

Newest `date` first. The explorer groups posts under their `folder` heading (`[-] NOTES/` collapses). Entries without `folder` fall back to `posts/<file>` under `MISC/`.

## Showcase a repo

Add one object to `repos.json`:

```json
{
  "name": "my-app",
  "repo": "you/my-app",
  "url": "https://github.com/you/my-app",
  "description": "One-line pitch for the PROJECTS list"
}
```

`branch` is optional — the repo's default branch is used. Clicking a project opens it in-page: the README renders in the post view and the FILES tab shows the full file tree. Any text file renders (markdown, highlighted code with line numbers, images). Binary files, files over 400 KB, and SVGs link out to GitHub instead. Unauthenticated GitHub API traffic allows roughly 60 repo loads per hour per IP.

## The chrome around posts

- Top bar, left box: `CURRENT POST` (or `CURRENT PROJECT` in a repo) plus the file name being viewed.
- Top bar, centre box: word count, read time, and the block progress bar.
- Top bar, right box: session clock. Boxes appear on wide screens only.
- Explorer: `DIRECTORY` with `> filter…` search across posts and repos. The `POSTS` tab holds topic-grouped posts; the `PROJECTS` tab holds your repos with each selected repo's file tree below the list.
- Code blocks get `[LANG]` labels, `[COPY]` buttons (clean text, no line numbers), syntax highlighting, and inline line numbers that travel with the code.

## About me block

The `ABOUT ME` section under the post list is plain Markdown — edit `about.md` in the repo root, no HTML needed:

```md
A few lines about whoever runs this blog. **Bold**, *italic*,
and [links](https://github.com/you/) all render here.

[GitHub](https://github.com/you/)
```

It renders on every page load with the same Markdown engine as posts. The lone `[GitHub](url)` last line is special: it sets where the `GITHUB ↗` box button points (and is consumed, so it never shows in the bio). The heading around it lives in `index.html`. The blinking robot beside the build credit is inline SVG (`.bot` in `style.css`) — keep him, he earns his pixels.

## Deploy

```bash
git add . && git commit -m "new post: my-new-post" && git push
```

In GitHub: **Settings → Pages → Deploy from branch → `main` / `/ (root)`**. That's it. No build command.

## Files you can ignore

- `index.html` — layout skeleton and explorer panes
- `style.css` — DOS/ANSI theme, tweak `:root` vars
- `app.js` — loader, search, tabs, GitHub backend, works as-is
- `posts.json` — post index, newest first
- `repos.json` — portfolio index for PROJECTS
- `.nojekyll` — tells Pages to serve files exactly as-is
