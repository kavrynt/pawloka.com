# pawloka.com

The marketing site for [Pawloka](https://pawloka.com/), a WhatsApp front desk for vet
clinics. It's a single static page, `site/index.html`, with inline CSS and a few lines of
JavaScript. There's no build step, and the only outside dependency is Google Fonts.

## Preview locally

```bash
python3 -m http.server 8000 --directory site   # http://localhost:8000
```

## Publishing

Everything in `site/` is published to https://pawloka.com/ by
`.github/workflows/deploy.yml` on every push to `main`. Pull requests run the same
check but don't deploy.

Make changes on a `feature/<name>` branch and open a pull request into `main`.

## Sign-up form

The form posts JSON to the URL in its `data-endpoint` attribute. While that attribute is
empty, the form tells visitors it isn't connected yet and sends nothing.

## Licence

Copyright © 2026 Pawloka. All rights reserved. The source is public so the site can be
hosted on GitHub Pages; it isn't open source, and no licence to reuse it is granted.
