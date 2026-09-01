# opsguy.io

Personal blog and portfolio site for Brandon Cantrell.

## Stack

- [Hugo](https://gohugo.io/) (static site generator)
- [Congo](https://github.com/jpanther/congo) theme
- Hosted on AWS (S3 + CloudFront)

## Local Development

Requires Hugo extended edition and Go.

```bash
cd site
hugo server -D
```

Site runs at http://localhost:1313

## Deployment

The GitHub Actions workflow works as follows:
1. Pull requests to `main` build the site with Hugo for validation.
2. Pushing a version tag (for example, `v1.3`) builds and deploys the static
   site to Cloudflare Pages.

Before the first production deploy, create a **Direct Upload** Cloudflare Pages
project named `opsguy-io` with `main` as its production branch. In GitHub, add
these repository secrets:

- `CLOUDFLARE_API_TOKEN`: an account-scoped API token with Cloudflare Pages
  **Edit** permission (use an API token, not a Global API key).
- `CLOUDFLARE_ACCOUNT_ID`: the Cloudflare account ID that owns the Pages
  project.

After the first deployment, attach `opsguy.io` in the Pages project's Custom
domains settings.

## Creating Content

```bash
# New blog post
cd site && hugo new posts/my-post-title/index.md

# New page
cd site && hugo new pagename/index.md
```

## Photo galleries

Photo posts are page bundles: put `index.md` and its images in the same folder.
The reusable `gallery` shortcode renders every image in that folder as a
responsive grid with captions and an expand-on-click view.

```text
site/content/posts/cooking-over-the-years/
├── index.md
├── first-sourdough-loaf.jpg
└── smoked-brisket.jpg
```

Use `{{< gallery >}}` to show all images, or choose the display order with
`{{< gallery images="first-sourdough-loaf.jpg,smoked-brisket.jpg" >}}`.
