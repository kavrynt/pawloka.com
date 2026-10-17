# pawloka.com

The marketing site for [Pawloka](https://pawloka.com/), a clinic suite for vets built on one
health record per pet, with a WhatsApp front desk for clients. What the page claims as live,
building, next or later follows the product docs in `kavrynt/pawloka-cloud` (the platform HLD,
the roadmap and ADR 0016 for the Basic and AI plans); update both together. It's a single static page, `site/index.html`, with inline CSS and a few lines of
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

## Hero video

`site/media/pets-hero.webm` and `pets-hero.mp4` are one 24-second loop cut from four
[Mixkit](https://mixkit.co/) clips under the Mixkit Stock Video Free License (ids 101229,
4103, 101218 and 22732). `pets-hero.jpg` is its poster frame. The video only loads when the
visitor hasn't turned on reduced motion or data saving, and it has a pause button.

## Sign-up form

The form posts JSON to the URL in its `data-endpoint` attribute. While that attribute is
empty, the form tells visitors it isn't connected yet and sends nothing. Clinics also send
`vets`, `plan` (`not-sure`, `basic` or `ai`) and an optional `software`; other roles don't.

## Licence

Copyright © 2026 Pawloka. All rights reserved. The source is public so the site can be
hosted on GitHub Pages; it isn't open source, and no licence to reuse it is granted.
