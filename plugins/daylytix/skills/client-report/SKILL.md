---
name: client-report
description: "Write a plain monthly SEO and AI-visibility report for a client from Daylytix data: Search Console clicks and impressions against the period before, Google Analytics organic and AI traffic, the audit score, and the next steps. Use when the user asks for a client report, a monthly report, or a summary of how a site is doing."
---

# Daylytix client report

## Goal

A report a business owner reads in two minutes: what changed, the likely reason, and what happens next. Every number has its source and dates.

## Gather

Ask for the site and the period if they are not clear (default: the last 28 days against the 28 before).

1. `get_project_memory`: the client's goals and key pages, and notes on work done.
2. Search Console, two calls with the same `group_by`:
   - `get_search_performance` `group_by` 'date' for the period, and again with `start` and `end` for the period before. Compare the totals.
   - `group_by` 'page' and 'query' for the period, to name what grew and what fell.
   - For year-on-year, give `start` and `end` a year back. When Daylytix keeps the site's history the answer can reach past Google's 16 months; the answer says where the data came from.
3. Google Analytics: `get_analytics` with `report` 'overview', then 'landing_pages', then 'ai_referrals'.
4. `list_audits` for the domain: the newest score and the one before, then `get_audit_summary` for the newest.
5. `get_prompt_tracker_latest` if the client tracks AI answers.

## Write

In the client's language, short sentences, no jargon (explain any term you must use):

1. **The headline**: clicks, impressions and organic sessions against the period before, as numbers and percent.
2. **What moved**: up to 3 pages or queries that grew and 3 that fell, with a likely reason only when the data shows one (a fixed page, a new page, a seasonal query). Say "not clear yet" when it is not.
3. **AI**: sessions from AI assistants, and whether AI answers named the brand.
4. **Site health**: the audit score now and before, and the one or two problems that matter.
5. **Next**: 3 steps for the coming month.

## Rules

- No number without its source and dates. Search Console data is about 3 days behind.
- Never claim a cause you cannot show. Correlation is not a reason.
- Do not promise rankings, traffic or AI mentions.
