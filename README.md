# Audio Mirror website

`index.html` is the whole site. One file, no build step, no dependencies — the
screenshots and the icon are embedded as data URIs, so it works from any static
host or straight off a USB stick.

`privacy.html` is the same privacy policy on its own page. The Microsoft Store
asks for a privacy policy **URL**, and a dedicated page is cleaner to hand a
reviewer than an anchor into the middle of a marketing page.

## Hosting it

Any static host works. Free options, roughly easiest first:

**GitHub Pages** — create a repository, put both files in it, then Settings →
Pages → deploy from branch. You get
`https://<user>.github.io/<repo>/`, and the privacy URL is that plus
`privacy.html`.

**Cloudflare Pages / Netlify** — drag the `web` folder onto their dashboard.
Both give a free subdomain and will attach a custom domain later.

**Your own domain** — upload both files to the web root.

## Before it goes live

- The Store button says **"Coming to the Microsoft Store"** and links to
  `https://apps.microsoft.com/detail/9NLM9BR7RPD3`. That link only resolves once
  the submission is published — change the label to "Get it from the Microsoft
  Store" then.
- The privacy policy carries a date. Update it if the policy changes.
- The contact address is `tlechner93@gmail.com`. Swap it for a support address
  if you would rather not publish a personal one.

## Design notes

Dark by default, because that is the app's own identity — near-black panel,
`#E03A3A` red. A light palette is defined for viewers whose system asks for one;
both are driven from the same custom properties, so changing an accent means
changing two values rather than hunting through rules.

Type is Saira for headings, Source Sans 3 for body, JetBrains Mono for channel
labels and figures. The mono face is doing real work: `FL FR C LFE BL BR` are
the actual Windows speaker names, and they read as data rather than decoration.

The numbered "signal path" is the only numbered thing on the page, because it is
the only part that genuinely is a sequence — the order the audio travels.
