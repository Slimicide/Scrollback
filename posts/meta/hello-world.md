# Hello, minimal blog

This is a blog that refuses to get in the way. No framework, no build step, no database. Just **markdown files**, two small JSON indexes, and static files.

> If you can write markdown and `git push`, you can run this blog.

## Why so minimal?

- **Lightweight:** `index.html` + `style.css` + `app.js` ≈ 50 KB. Only dependencies are `marked` and `highlight.js` via CDN for rendering.
- **GitHub Pages native:** push this folder to `main` and enable Pages. No Jekyll, no Actions needed.
- **Dark by default:** blackish `#0a0a0c` background, bright `#d7d7db` text — easy on the eyes, high contrast where it matters.
- **Portfolio ready:** the `PROJECTS` tab browses real GitHub repos in-page — READMEs render like posts and every text file opens with highlighting.

## How it works

1. Write `posts/notes/my-idea.md`
2. Drop images in `images/notes/my-idea/`
3. Add one entry to `posts.json`
4. Push. Done.

The explorer on the left is generated automatically from `posts.json`, grouped by topic folder. Try the filter box — it searches posts and repos. Full maintenance guide lives in `GUIDES/`.

---

Next: see the [Markdown showcase](#/markdown-showcase) for every element this theme supports.
