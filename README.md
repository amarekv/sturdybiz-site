# sturdybiz.com

The product site. Separate from the application (`app.sturdybiz.com`, repo
`amarekv/sturdybiz`) on purpose: different release cadence, and marketing
scripts never share a host with signed-in sessions.

- Served by GitHub Pages from `main`, built by Jekyll.
- Every link target and the contact address are in `_config.yml`; edit them
  there, not in `index.html`.
- `CNAME` holds the custom domain GitHub Pages serves.

## DNS (Namecheap > Domain List > sturdybiz.com > Advanced DNS)

Add, leaving the existing `app` A record and the Private Email MX/TXT records
untouched:

| Type  | Host | Value               |
|-------|------|---------------------|
| A     | @    | 185.199.108.153     |
| A     | @    | 185.199.109.153     |
| A     | @    | 185.199.110.153     |
| A     | @    | 185.199.111.153     |
| CNAME | www  | amarekv.github.io.  |

Then in the repo's Settings > Pages, tick **Enforce HTTPS** once the
certificate is issued. GitHub redirects `www` to the apex automatically.

## Preview locally

Open `index.html` through Jekyll (`bundle exec jekyll serve`), or just push:
the `{{ site.* }}` tags are filled in only when Jekyll builds the page.
