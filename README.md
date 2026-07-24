# qilinli.github.io

Source for [Dr Qilin Li's](https://qilinli.github.io) personal academic website — Senior Lecturer and ARC DECRA Fellow at Curtin University, working on AI for intelligent infrastructure and structural health monitoring.

Built with [Jekyll](https://jekyllrb.com/) on the [Academic Pages](https://github.com/academicpages/academicpages.github.io) template, deployed via GitHub Pages.

## Local development

```bash
bundle install
bundle exec jekyll serve
```

Then open <http://localhost:4000>.

## Structure

- `_pages/` — About (homepage), Research, Publications, Talks, Teaching, 404
- `_publications/`, `_talks/`, `_teaching/` — collection entries (one file per item)
- `_data/navigation.yml` — header navigation
- `_config.yml` — site configuration
