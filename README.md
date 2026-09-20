# A Letter for Sana

A single static page: a drifting golden-cloud sky, a sealed envelope, and a handwritten
letter that slides out when you click it.

Everything lives in `index.html` — no build step, no dependencies. The only external
request is the Google Fonts stylesheet (Caveat, Homemade Apple, Cormorant Garamond).

## Editing the letter

Open `index.html` and look for `<article class="sheet">`. The whole letter is plain HTML
in there: the date, the salutation, three numbered points, the sign-off, the P.S.

Quick things you'll probably want to change:

| What | Where |
| --- | --- |
| The sign-off name (`— K`) | `<p class="closing">` |
| The date | `<p class="date">` |
| Envelope front (`Sana`, `to be opened on day one`) | `<span class="env__addr">` |
| Wax seal letter (`S`) | `<span class="env__seal">` |
| Drop the P.S. | delete `<p class="ps">` |

## Deploying to Cloudflare Pages

**Option A — connect the repo (auto-deploys on every push)**

1. Cloudflare dashboard → Workers & Pages → Create → Pages → Connect to Git
2. Pick this repo and branch
3. Framework preset: **None**. Build command: leave empty. Build output directory: `/`
4. Save and Deploy

**Option B — one command from this folder**

```sh
npx wrangler pages deploy . --project-name for-sana
```

First run opens a browser to authorize your Cloudflare account and creates the project.
You get a `https://for-sana.pages.dev` URL; add a custom domain later under the project's
Custom domains tab if you want.

## Local preview

```sh
python3 -m http.server 8000
# then open http://localhost:8000
```
