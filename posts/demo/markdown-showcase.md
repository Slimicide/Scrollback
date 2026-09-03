# Markdown showcase

Every common markdown element, styled for a dark, professional look.

## Typography

Normal paragraph with **bold**, *italic*, ~~strikethrough~~, and a [link](https://example.com). Inline code looks like `const x = 1` and keyboard input like <kbd>⌘K</kbd>.

> A blockquote for pull-quotes and callouts.
> Keeps its cool with a white left border and a subtle panel.

## Code blocks

```js
// copy button appears automatically
export async function loadPost(slug) {
  const res = await fetch(`posts/${slug}.md`);
  const md = await res.text();
  return marked.parse(md);
}
```

```python
def hello(name="world"):
    print(f"hello, {name} — tables below still align")
```

```bash
# deploy to GitHub Pages
git add . && git commit -m "new post" && git push
```

## Wide code (scroll test)

Scroll this block right: the `[JS]` label row and dashed rule hold the visible frame while code and line numbers slide together underneath — no overlays, nothing left behind. `[COPY]` still grabs clean text without numbers.

```js
const SERVICES = ["authentication-service-primary", "notification-dispatcher-secondary", "billing-reconciliation-worker", "search-indexer-canary"];
const DSN = "https://0123456789abcdef0123456789abcdef@telemetry.example.com/0123456789";
function route(host) { return "https://" + host + ".internal.example.com:8443/api/v2/ingest?token=0123456789abcdef&format=json&compress=zstd"; }
```

## Table

| Element       | Syntax          | Renders   |
|---------------|-----------------|-----------|
| Inline code   | `` `code` ``    | `code`    |
| Bold          | `**bold**`      | **bold**  |
| Image         | `![alt](src)`   | see below |
| Task          | `- [ ] todo`    | ☐ todo    |

## List & tasks

- Minimal to maintain
- Fast to load
- Easy to extend

1. Write markdown
2. Add to `posts.json`
3. Push to Pages

- [x] Dark theme
- [x] Post explorer + search
- [ ] Your next post

## Image (per-post folder)

![Demo graphic](images/demo/markdown-showcase/demo.svg)

Images live in `/images/<topic>/<slug>/`. Reference them root-relative as `images/<topic>/<slug>/file.png` — or place them next to your post and use `./file.png`, which resolves against the post's own folder.

---

That's everything. If it renders here, it'll render on GitHub Pages.
