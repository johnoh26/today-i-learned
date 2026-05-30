# Today I Learned

A Jekyll blog of daily notes on tech, investing, and life.

> Inspired by Haruki Murakami's daily writing routine and Charlie Munger's habit of going to bed a little smarter every day.

**Live site:** [johnoh.is-a.dev](https://johnoh.is-a.dev) · **Theme:** [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/)

---

## Adding a New Post

### 1. Create the file

All posts live in `_posts/`. The file name must follow this exact format:

```
_posts/YYYY-MM-DD-short-title-slug.md
```

Examples:
```
_posts/2022-04-07-rpc-101.md
_posts/2022-03-29-caching-strategies.md
_posts/2022-01-05-design-patterns.md
```

Rules:
- Date must match the `date:` field in the front matter
- Slug is lowercase, hyphen-separated, no special characters
- Keep it short (3–5 words max)

### 2. Add front matter

Every post must start with a YAML front matter block:

```yaml
---
title: "Your Post Title"
date: YYYY-MM-DD
categories:
  - tech          # tech | investing | personal
tags:
  - networking    # see tag list below
  - protocols
excerpt: "One sentence that summarizes the post. Shows up in the home feed."
---
```

### 3. Write the content

Plain markdown below the front matter. Short bullet lists work great:

```markdown
- First thing I learned
- Second thing I learned
- Third thing I learned
```

For longer posts, use headers (`##`) to organize sections.

---

## Categories

Use one or more of:

| Category | When to use |
|----------|-------------|
| `tech` | Programming, system design, networking, databases, frameworks |
| `investing` | Markets, compounding, mental models, portfolio strategy |
| `personal` | Life reflections, career thoughts, goals, family |

---

## Tags

Common tags already in use:

**Tech:** `networking` · `protocols` · `tcp` · `udp` · `dns` · `osi-model` · `system-design` · `cdn` · `caching` · `databases` · `sql` · `nosql` · `scalability` · `architecture` · `microservices` · `distributed-systems` · `ddd` · `design-patterns` · `clean-code` · `dotnet` · `csharp` · `aspnet` · `async` · `testing` · `debugging` · `visual-studio` · `javascript` · `typescript` · `angular` · `rxjs` · `css` · `web` · `api` · `jwt` · `security` · `authentication` · `azure` · `cs-fundamentals` · `systems`

**Investing:** `compounding` · `mental-models`

**Personal:** `career` · `startup` · `entrepreneurship`

You can add new tags freely — they'll automatically appear in the Tags archive.

---

## Preview Locally

Requires Ruby and Bundler:

```bash
bundle install
bundle exec jekyll serve
```

Then open `http://localhost:4000`.

---

## Deployment

The site is deployed automatically via GitHub Pages on every push to `main`. No action needed — just push.
