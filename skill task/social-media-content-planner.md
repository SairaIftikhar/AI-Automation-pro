---
name: social-media-content-planner
description: Generates an organized social media content plan (calendar) for small businesses and freelancers so they don't have to think up new post ideas every day. Produces a rotating mix of content categories (product showcase, educational, behind-the-scenes, testimonial, promotional, etc.) with a caption, hook, call-to-action, suggested format, and hashtags for each post. Make sure to use this skill whenever the user asks for a "social media plan," "content calendar," "post ideas," "what should I post this week/month," help planning Instagram/TikTok/LinkedIn/Facebook content, or wants to organize content for a business, client, or personal brand — even if they don't use the words "content calendar" explicitly.
---

# Social Media Content Planner

Helps small businesses, freelancers, and social media managers turn a blank page into a ready-to-use content plan.

## Workflow

### 1. Gather inputs

If the user hasn't already provided these, ask for them (batch into one or two questions rather than five separate turns):

- **Business type** — what the business does (e.g. "homemade bakery," "freelance graphic designer," "yoga studio")
- **Target audience** — who they're trying to reach
- **Product/service** — what specifically they want to promote
- **Marketing goal** — e.g. brand awareness, sales, engagement, client retention
- **Platform(s)** — Instagram, TikTok, LinkedIn, Facebook, etc. (can be more than one)
- **Timeframe** — always ask if not given (e.g. "one week," "one month"). Don't default silently — the plan length changes the workload, so confirm with the user.

If the user gives a partial answer (e.g. just "I run a bakery, help me with Instagram"), ask only for what's missing.

### 2. Generate the plan

Use a rotating mix of content categories so the plan doesn't feel repetitive. Core categories to draw from:

- **Product/service showcase** — highlight a specific item or offering
- **Educational** — tips, how-tos, myth-busting relevant to the niche
- **Behind-the-scenes** — process, team, workspace
- **Customer testimonial / social proof** — reviews, results, UGC
- **Promotional** — offers, discounts, launches
- **Engagement** — polls, questions, UGC prompts
- **Community/trend** — timely, seasonal, or trending tie-ins

Distribute categories across the timeframe so no single category dominates (e.g. don't run "promotional" more than 1-2x/week unless the user's goal is sales-focused).

**If multiple platforms are requested, create a separate plan per platform** — don't merge them into one table. Tailor format suggestions and tone to each platform's norms (e.g. TikTok skews short-form video/trend-driven, LinkedIn skews professional/text-forward, Instagram balances visual + caption).

For each post, include:

| Field | Description |
|---|---|
| Day/Date | Which day in the timeframe |
| Content Category | e.g. Educational, Behind-the-scenes |
| Content Idea | One-line concept |
| Hook | Opening line/visual concept to stop the scroll |
| Caption | Full draft caption, matching a plausible brand voice for the business type |
| Call-to-action | What the viewer should do next |
| Suggested Format | e.g. Reel, carousel, static post, Story |
| Hashtags | 8-12 hashtags, mixed by reach tier (see below) |

**Hashtag mix.** For every post, blend three tiers rather than only niche tags:

- **Broad/high-volume** (2-3 tags, millions of posts) — general category tags that pull in scale and discovery, e.g. `#foodie`, `#smallbusiness`, `#instagood`
- **Niche/community** (3-4 tags, tens/hundreds of thousands) — specific to the content category or product, e.g. `#homemadebakery`, `#cakedecorating`
- **Local/branded** (2-3 tags) — city/neighborhood tags and a business-specific or campaign tag, e.g. `#[city]eats`, `#[bakeryname]`

Broad tags shouldn't be generic filler — pick ones that are genuinely active and relevant to the post's content or platform trends at time of writing, not just the widest possible tag. Note in the response that hashtag trends shift, so the user should periodically check what's currently active on their platform rather than treating this list as permanent.

### 3. Deliver the plan

Always deliver **both**:

1. **Chat preview** — render the plan as a markdown table directly in the response so the user can review it immediately.
2. **Downloadable file** — build the same plan into a `.xlsx` spreadsheet (one sheet per platform if multiple were requested) so the user can hand it to a client or edit it directly. Read `/mnt/skills/public/xlsx/SKILL.md` before creating the file. Save it to `/mnt/user-data/outputs/` and present it with `present_files`.

### 4. Offer follow-up

After delivering the plan, briefly offer to: regenerate any single day's post, extend the timeframe, adjust tone/voice, or add another platform. Don't over-explain — keep this to one short line.

## Notes

- Keep captions realistic in length and voice for the platform and business type — a bakery's Instagram caption should read differently from a B2B consultant's LinkedIn post.
- Don't invent specific facts about the business (exact prices, real testimonials, real addresses) — use placeholders like "[price]" or generic phrasing the user can fill in, unless they've given you real details.
- If the user only wants ideas/topics without full captions, they'll say so — otherwise always fill in all six fields per post, since that's the default value-add of this skill.
