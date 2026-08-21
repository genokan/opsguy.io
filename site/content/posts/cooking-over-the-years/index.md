+++
date = 2026-08-21
title = "Cooking Over the Years"
description = "A work-in-progress look at the meals, experiments, and small victories from my kitchen."
tags = ["cooking", "food"]
draft = true
+++

This is the story of how I learned to cook: the experiments that worked, the ones
that absolutely did not, and the meals worth making again.

<!--more-->

## The early days

Add your first section here, then place the photos for this post in this same
folder alongside `index.md`.

Use the gallery wherever a group of photos belongs in the story:

```go-html-template
{{</* gallery */>}}
```

By default it displays every image in this post's folder. To choose the order or
show only particular images, list the filenames:

```go-html-template
{{</* gallery images="first-loaf.jpg,smoked-brisket.jpg,pasta-night.jpg" */>}}
```

Image filenames become the caption and alt text, so descriptive names such as
`first-sourdough-loaf.jpg` read nicely. Remove `draft = true` when you are ready
to publish.
