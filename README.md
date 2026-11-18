# retroforge.org

The source of [retroforge.org](https://retroforge.org), built with [Zensical](https://zensical.org).

## Working on the site

```sh
python3 -m venv .venv
.venv/bin/pip install -r requirements.txt
.venv/bin/zensical serve
```

Then open <http://localhost:8000>. Pages live in `docs/`, the navigation and theme in `zensical.toml`, and the brand colours in `docs/stylesheets/extra.css`.

## Publishing

Every push to `master` builds the site and publishes it to GitHub Pages through `.github/workflows/docs.yml`. The repository's Pages source must be set to **GitHub Actions** (Settings › Pages). The custom domain comes from `docs/CNAME`.
