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

Push to `main` triggers GitHub Actions workflow:
1. Builds site with Hugo
2. Syncs to S3
3. Invalidates CloudFront cache

PRs to `main` run the build for validation but don't deploy.

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
