# Editing guide

Your site is split into small files. GitHub Pages stitches them
together automatically with Jekyll — you don't run any build tool.
Just edit a file, commit, and push (or edit right on GitHub).

> Note: the include tags in the examples below are written with
> full-width brackets `｛% ... %｝` on purpose, so this guide itself
> doesn't get processed by Jekyll. In the real `index.html` they use
> normal brackets `{% ... %}`. `_config.yml` also tells Jekyll to skip
> this file, so it can't break the build.

## File map

```
index.html            Page skeleton. You rarely touch this — it just
                      lists which section to include, in order.
style.css             ALL styling (colors, fonts, spacing). Edit here
                      to change how things look.
_config.yml           Tells GitHub Pages to build with Jekyll. Leave it.
_includes/
  nav.html            Top navigation bar
  hero.html           Name (incl. 中文名), photo, intro, the
                      "seeking internship" box, and social links
  research.html       Research paragraph + Research Keywords
  news.html           News list
  publications.html   Publication entries
  experience.html     Experience & Teaching entries
  footer.html         Footer
```

## Common edits

- Add a publication -> open `_includes/publications.html`, copy one
  whole `<div class="pub-entry"> ... </div>` block, and fill in your
  title, authors, venue, tags, and abstract.
- Change the research paragraph or keywords -> `_includes/research.html`.
- Add or edit an experience -> `_includes/experience.html`, copy one
  `<div class="exp-item"> ... </div>` block.
- Add a news line -> `_includes/news.html`.
- Change your name or the intro -> `_includes/hero.html`.
- Change a color -> `style.css`, edit the variables in `:root`
  (`--blue` is the primary teal; `--purple` is the darker teal used
  for hovers and labels; `--green` is the accent green).

## How the stitching works

`index.html` contains lines like `｛% include hero.html %｝`. When you
push, GitHub replaces each of those with the matching file from
`_includes/`. So the order of sections is controlled by `index.html`,
and the content of each section lives in its own file.

## Company logos (Experience)

Each entry shows a rounded square with a letter as a placeholder,
e.g. `<div class="exp-logo">R</div>`. To use a real logo, put the
image in `images/` and replace that line with:

```html
<img class="exp-logo" src="images/your-logo.png" alt="" />
```

## Paper teaser images (Publications)

Each entry has a placeholder thumbnail. To use a real teaser image,
replace the `<div class="thumb-ph"> ... </div>` block with:

```html
<img src="images/your-teaser.png" alt="Paper teaser" />
```

## Important

- Don't add a file named `.nojekyll` to the repo — it turns off the
  stitching and you'd see raw include tags on the page.
- `index.html` must keep the two `---` lines at the very top; that's
  what tells GitHub Pages to process the includes.
- If a build ever fails, open the **Actions** tab, click the failed
  run, expand the error, and read the last line — it usually names
  the file and the problem.
