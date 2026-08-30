# Editing guide

Your site is now split into small files. GitHub Pages assembles them
automatically with Jekyll — you don't run any build tool. Just edit,
commit, push.

## File map

```
index.html            Page skeleton. You rarely touch this — it just
                      lists which section to include, in order.
style.css             ALL styling (colors, fonts, spacing). Edit here
                      to change how things look.
_includes/
  nav.html            Top navigation bar
  hero.html           Name, photo, intro, "seeking interns" box, links
  research.html       Research paragraph + Research Keywords
  news.html           News list
  publications.html   Publication entries
  experience.html     Experience & Teaching entries
  footer.html         Footer
_config.yml           Tells GitHub Pages to build with Jekyll. Leave it.
```

## Common edits

- Add a publication  -> open `_includes/publications.html`, copy one
  `<div class="pub-entry">…</div>` block, fill in your info.
- Change research keywords -> `_includes/research.html`.
- Add an experience -> `_includes/experience.html`, copy one
  `<div class="exp-item">…</div>` block.
- Change a color -> `style.css`, edit the variables in `:root`
  (e.g. `--blue` is the primary teal).

## Company logos (Experience)

Each entry shows a rounded square with a letter as a placeholder:
`<div class="exp-logo">R</div>`. To use a real logo, put the image in
`images/` and replace that line with:
`<img class="exp-logo" src="images/your-logo.png" alt="" />`

## Important

- Do NOT add a file named `.nojekyll` to the repo — it turns off the
  assembly and you'd see raw `{% include %}` text on the page.
- `index.html` must keep the two `---` lines at the very top; that's
  what tells GitHub Pages to process the includes.
