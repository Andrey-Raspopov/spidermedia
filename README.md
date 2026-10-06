# SpiderMedia.ru — архив

Архивная копия редакционных материалов сайта [spidermedia.ru](http://spidermedia.ru/)
(2003–2026), восстановленная из [Wayback Machine](https://web.archive.org/web/*/spidermedia.ru)
и переведённая в Markdown.

An archive of the editorial content of spidermedia.ru, a Russian comics and pop-culture site,
rebuilt from Wayback Machine snapshots taken up to 14 March 2026 and converted to Markdown.

## What is here

- `content/` — one Markdown file per article, at the same path as on the original site
  (`/news/<slug>` → `content/news/<slug>.md`). Front matter records the title, date,
  original URL and the exact Wayback snapshot the text was taken from.
- Three generations of the site are covered: the early static site (2003–2007, converted
  from Windows-1251), the Drupal site (2008–2013) and the later custom CMS (2014–2026).
- Not included: the phpBB forum, user profiles, login/search pages and auto-generated
  tag listings.

## Tags and search

- Tags come from the original articles (both the Drupal and the later CMS used `/tags/<slug>`),
  so tag pages keep their original addresses: `/tags/marvel/`, `/tags/hellboymedia/`, …
  `content/tags/<slug>/_index.md` holds each tag's display name.
- Search is a static [Pagefind](https://pagefind.app/) index built after Hugo in the deploy
  workflow, with Russian stemming and filters by section and year. Only article bodies are indexed.

## Images and audio

Images and podcast audio are not stored in this repository (about 6 GB, over GitHub Pages'
size limit). They are linked to their Wayback Machine snapshots; images hotlinked from other
hosts point to the archive's capture nearest to the date of the page.

## Cleanup applied

Analytics and counters (Yandex.Metrika, Google Analytics, LiveInternet, Mail.ru, Rambler Top100,
HotLog), ad networks (AdSense, Sape, uptolike, relap) and dead widgets were removed. Flash
YouTube players were replaced with modern YouTube embeds; other Flash content and embeds from
services that have shut down were replaced with a link to the original file.

## Building

The site is built with [Hugo](https://gohugo.io/) by `.github/workflows/pages.yml` on every
push to `main`. Locally:

```sh
hugo -d public/spidermedia && npx -y pagefind@1.5.2 --site public/spidermedia
python3 -m http.server -d public    # then open http://localhost:8000/spidermedia/
```

(`hugo server` works too, but without search: the Pagefind index only exists after a build.)
