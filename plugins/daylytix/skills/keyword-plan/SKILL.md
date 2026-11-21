---
name: keyword-plan
description: "Build a keyword plan for a site from its own Search Console data first, then from competitors and keyword ideas: which existing pages to improve for which queries, and which new pages to write. Use when the user asks for keyword research, content ideas, a content plan or what to write next."
---

# Daylytix keyword plan

## Goal

A short plan the user can act on: a list of pages, each with the queries it should win and why. Start from the site's own data, which is free and real. Use paid data only where it adds something.

## 1. The site's own demand (free)

1. `get_project_memory`: the business, audience, goals, competitors and key pages.
2. `get_search_performance` with no `site` lists the connected sites. Then, for the site:
   - `group_by` 'query', `days` 90: what people already search to find it.
   - `group_by` 'query_page', `days` 90: which page shows for which query. Two pages showing for the same query is a sign they compete.
3. `get_search_opportunities`: queries at positions 4 to 20 (the cheapest wins), pages with low CTR, queries losing clicks.
4. `get_saved_keywords`: what the user already chose in Keyword Research.

## 2. Outside demand (uses the account's own DataForSEO credits)

These tools count toward 60 data requests a day through MCP; a cached answer is free. Tell the user before you make several calls.

- `find_competitors`, then `get_content_gap` with 1 to 3 of them: queries they rank for and the site does not.
- `get_ranked_keywords` for a competitor's strongest pages.
- `get_keyword_ideas` with 1 to 10 seeds from the business itself, not only from competitors.

If the account has no DataForSEO login, say so and plan from step 1 alone.

## 3. Group into pages

- Group queries that the same page can answer (one search intent), not just queries that share words.
- For each group decide: improve an existing page (name the URL) or write a new one.
- Order by: demand the site can realistically win (position, difficulty, how close existing pages are), then fit with the business goals.

## Write

A table: page (existing URL or proposed title), target queries, current position and impressions where known, monthly volume where known, why, and what to change. Then 3 lines on what to do first. Name the source and dates of every number.

## Rules

- Never invent volumes or positions. Mark a number as an estimate when it comes from DataForSEO.
- Save the plan's key pages with `update_project_memory` only after the user agrees.
