---
name: lead-finder
description: Finds small business websites that do NOT yet have a chatbot or AI call/voice agent, and compiles a lead list with the business's own publicly listed contact info (owner/contact name, email, phone) so they can be pitched on chatbot/voice-agent services. Use this skill whenever the user asks to "find leads," "find businesses without a chatbot," "find prospects for my agency," "who doesn't have a chatbot yet," or wants a list of websites to cold-pitch chatbot/voice-agent/AI-agent offerings — even if they just say "find me some leads" without spelling out the criteria.
---

# Lead Finder

Finds small-business websites that are missing chatbot/AI-voice-agent functionality, and builds a lead list of publicly available contact info from each business's own site — for pitching chatbot/call-agent services.

## Scope and ethics guardrails

- Only use **publicly listed business contact info** found on the business's own website (Contact page, About page, footer, header). Never use WHOIS lookups, scraping of personal/private data, or any info not voluntarily published by the business for public contact purposes.
- Never fabricate or guess an email address (e.g. never generate `info@` or `firstname@domain` unless it's actually displayed on the site).
- These are business inquiries for B2B outreach, not personal data — skip any listing that looks like a personal (non-business) site.
- Mention to the user once per session (not every run) that they're responsible for complying with applicable anti-spam laws (e.g. CAN-SPAM, GDPR/PECR if contacting EU/UK businesses) when they actually send outreach.

## Workflow

1. **Clarify scope if not given.** If the user hasn't specified an industry/niche and/or location, ask (one question, e.g. "Any particular industry or city, or should I search broadly?"). If they say "anything," proceed with a broad small-business search.

2. **Search for candidate businesses.** Use `web_search` with queries combining niche + location where given (e.g. `"dentists in Austin TX"`, `"family owned restaurants Lahore"`). Favor small/local/independent businesses over large chains or franchises — they're less likely to already have AI tooling and are a better fit for a cold pitch. Pull more candidates than the ~25 target since some will be filtered out (already have a chatbot, no public contact info, chain/franchise, etc.).

3. **Check each candidate site for an existing chatbot or AI voice/call agent.** `web_fetch` the homepage (and contact page). Look for signals such as:
   - Chat widget scripts/embeds: Intercom, Drift, Tidio, Crisp, LiveChat, Tawk.to, HubSpot chat, Zendesk chat, ManyChat, Chatbase, Voiceflow, Landbot
   - AI voice/call agent mentions: "AI receptionist," "virtual receptionist," phone widgets from Bland.ai, Synthflow, Vapi, Retell, Air.ai, or similar
   - A visible chat bubble/launcher in the fetched HTML, or text like "Chat with us," "Ask our AI assistant"
   - If any of these are present, **exclude this business** — it's not a lead, note it as filtered and move on.
   - If the fetch fails or the site is unreachable/broken, skip it (dead site isn't a useful lead either).

4. **Extract contact info from qualifying businesses.** From the site's Contact/About page (or footer), pull whatever is publicly published:
   - Business name
   - Contact/owner name (only if actually named on the site — otherwise leave blank, don't guess)
   - Email (only if displayed as text or mailto link on the page — never inferred)
   - Phone (if listed)
   - Website URL
   - One-line note on what the business does (helps personalize outreach later)

5. **Stop once you have ~25 qualifying leads** (or fewer if the niche/location is narrow — tell the user how many candidates were checked vs. how many qualified).

6. **Save results to an Excel file (.xlsx)** — do not print the leads as a table in chat. Consult the xlsx skill for how to build the spreadsheet correctly. Columns:
   `Business Name | Website | What They Do | Contact Name | Email | Phone | Notes`
   - Use "—" for any field that wasn't publicly available rather than leaving it blank or guessing.
   - In "Notes," flag anything relevant to the pitch (e.g. "very outdated site," "high review count, likely busy — good candidate for AI receptionist").
   - Name the file descriptively, e.g. `leads-dentists-austin.xlsx`, or `leads-<date>.xlsx` if no clear niche/location was given.
   - Save it to the outputs location and present it to the user as a downloadable file — don't paste the data into the chat message itself.

7. **Offer next steps** briefly in chat: e.g. drafting a cold outreach email/message for these leads, or running another batch with different criteria.

## Notes

- If a business's own site has no contact page at all, it's still a fine lead if a phone/email appears elsewhere on the site (e.g. footer) — only skip it if there's truly no public contact info at all.
- Don't count directory listings (Yelp, Google Maps profile pages) as "the business's website" — always find and check their actual owned website.
