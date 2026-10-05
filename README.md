# Karan Baijal's website

This is the source for [karanbaijal.github.io](https://karanbaijal.github.io/), hosted on GitHub Pages. The homepage is a research portfolio, and `/blog/` is a writing archive. The site's original portfolio format was derived from [Jon Barron's website](https://github.com/jonbarron/jonbarron_website).

## Publish a new article

Create `_posts/YYYY-MM-DD-your-slug.md`. The filename determines the permanent URL: this example becomes `/blog/your-slug/`. Keep the slug unchanged after publishing so existing links continue to work. Add front matter, followed by Markdown:

```markdown
---
title: "Your article title"
date: 2026-10-04
description: "A one-sentence summary for the archive and link previews."
related_project: "Project name"
related_project_url: "https://example.com/project"
---

Your article begins here.

## A section heading

Explain the problem, approach, evidence, limitations, and what you learned.
```

`title`, `date`, and `description` are required for the archive, homepage preview, and article metadata. The two `related_project` fields are optional; use both to show a related research link at the end of an article. Posts appear newest first on `/blog/`, and the latest two appear automatically on the homepage. The empty state disappears when the first post is published.

Put article images in `images/blog/` and refer to them with absolute site paths such as `/images/blog/your-image.png`. For a caption, use HTML in the Markdown file:

```html
<figure>
  <img src="/images/blog/your-image.png" alt="A useful description of the image">
  <figcaption>What the figure shows.</figcaption>
</figure>
```

Fenced code blocks work in Markdown. Use descriptive link text and image alt text, and link to relevant papers, demos, code, or research pages where helpful.

## Preview and publish

Use Ruby 3 and Bundler for a local preview:

```sh
bundle install
bundle exec jekyll serve
```

Visit `http://127.0.0.1:4000/` and `/blog/`. To publish, merge the change into the repository's configured GitHub Pages publishing branch. In **Settings → Pages**, confirm the source points to that branch and the repository root. GitHub Pages builds the Markdown into public HTML. Check the Pages deployment status, then verify the live homepage, `/blog/`, the article URL, `/feed.xml`, and `/sitemap.xml`.

Write the full article here first. If announcing it on Substack, send a short introduction and link to the article on this site rather than publishing a second full copy.
