The user has given you raw TIL notes to turn into a Jekyll blog post for the today-i-learned repo.

Here is their input:
$ARGUMENTS

Follow these steps:

1. **Determine today's date** using the currentDate from context (format: YYYY-MM-DD).

2. **Generate a title** — concise, title-cased, describing the main topic (e.g. "CAP Theorem and ACID Properties", "Angular Change Detection").

3. **Create a slug** from the title: lowercase, hyphens instead of spaces, no special characters (e.g. "cap-theorem-and-acid-properties").

4. **Choose categories** — one or more of:
   - `tech` — programming, system design, networking, databases, frameworks, tools
   - `investing` — markets, compounding, mental models, portfolio strategy
   - `personal` — life reflections, career thoughts, goals, family

5. **Choose tags** — pick relevant ones from the existing taxonomy, or add new ones if clearly needed. Common tags: `networking`, `protocols`, `tcp`, `udp`, `dns`, `osi-model`, `system-design`, `cdn`, `caching`, `databases`, `sql`, `nosql`, `scalability`, `architecture`, `microservices`, `distributed-systems`, `ddd`, `design-patterns`, `clean-code`, `dotnet`, `csharp`, `aspnet`, `async`, `testing`, `debugging`, `javascript`, `typescript`, `angular`, `rxjs`, `web`, `api`, `jwt`, `security`, `authentication`, `cs-fundamentals`, `career`, `startup`, `investing`, `compounding`, `mental-models`.

6. **Write a one-sentence excerpt** — summarizes the key takeaway, used in the home feed.

7. **Format the content** — clean up the raw notes into well-structured markdown. Use bullet points for lists of facts. Use `##` headers if there are clearly distinct sub-topics. Preserve the user's original wording as much as possible.

8. **Create the file** at `_posts/YYYY-MM-DD-slug.md` with this structure:
```
---
title: "Title Here"
date: YYYY-MM-DD
categories:
  - category
tags:
  - tag1
  - tag2
excerpt: "One sentence summary."
---

Formatted content here.
```

9. **Show the user the file** you created and ask if they want to commit and push it.
