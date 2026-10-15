# Heil Group website

Source of [cheil.github.io](https://cheil.github.io), the website of the Computational Material Design group of Christoph Heil at the Institute of Theoretical and Computational Physics, TU Graz.

The site is built with [Jekyll](https://jekyllrb.com/) and the [Petridish](https://github.com/peterdesmet/petridish) theme. Every push to `main` triggers a rebuild on GitHub Pages. To preview locally: `bundle install` once, then `bundle exec jekyll serve` and open <http://localhost:4000>.

## Where things live

| What | Where |
|---|---|
| Blog posts | `_posts/YYYY-MM-DD-<slug>.md` (URL: `/blog/YYYY/<slug>/`) |
| Publication list | `pages/research/publications.md` (newest first) |
| Research projects | `pages/research/projects.md` |
| Team and alumni | `_data/team.yml`, `_data/alumni_team.yml` |
| CV page | `pages/pi_cv.md` |
| Navigation and footer | `_data/navigation.yml`, `_data/footer.yml` |
| Images | `assets/theme/images/` (photos as JPEG, at most 2000 px wide) |
| Privacy page and cookie banner | `pages/privacy.md`, `_includes/cookie-consent.html` |

## Notes

- Post titles like "New preprint announcement" or "Paper published in ..." are combined with the post's `description` (the paper title) for the browser tab and search results; see `_includes/head.html`.
- `meta_description` in a page's front matter sets the text search engines show, without changing the subtitle on the page.
- Fonts (Lora) are self-hosted in `assets/theme/fonts/lora/`, so no request goes to Google Fonts.
- Content is licensed under CC BY 4.0; the theme code under the MIT license (`LICENSE`).
