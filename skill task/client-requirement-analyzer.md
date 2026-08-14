---
name: client-requirement-analyzer
description: Turns a messy, informal client message (from WhatsApp, email, a chat, a call transcript, or a verbal recap) into a structured project brief - identified requirements, missing information, clarifying questions to ask the client, and suggested next steps. Works for any freelance or agency service (web/app development, graphic design, writing, marketing, video, consulting, etc.), not just software projects. Make sure to use this skill whenever the user pastes or describes a client's request and wants it organized, whenever they say things like "here's what my client sent me," "can you make sense of this brief," "what should I ask them before I start," or "turn this into a project brief" - even if they don't use the word "requirements" explicitly.
---

# Client Requirement Analyzer

A skill for turning vague client asks into something a freelancer can actually act on: a short brief that separates what the client already told you from what you still need to find out.

## Why this matters

Clients rarely describe a project the way a developer or designer would spec it. They write like they'd talk to a friend: a couple of features, a vague vision, maybe a comparison to a competitor's site. Nothing about budget, timeline, platform, or scope. If a freelancer starts building from that message alone, gaps surface mid-project - which is expensive to fix and frustrating for both sides. The fix isn't to guess; it's to surface the gaps *before* work starts, as a short, clear list of questions.

## Process

Work through these steps in order. Don't skip straight to writing questions - the brief and the questions both depend on doing the categorization carefully first.

1. **Read the client's message closely.** Note not just what they explicitly ask for, but implied needs (e.g. "customers see products" implies photos, descriptions, and probably some kind of catalog structure - not just a single page).
2. **Identify the core objective.** One sentence: what is this project fundamentally for? (e.g. "an online storefront for a clothing brand," not "a website.")
3. **Extract every requirement the client explicitly stated.** Keep this list to things they actually said.
4. **Separately, note reasonable assumptions or implied needs** (e.g. "customers see products" implies photos and some catalog structure, not just a single page). Keep these distinct from what the client stated - a freelancer skimming fast needs to be able to tell "the client said this" from "I'm inferring this," since inferences can be wrong and need confirming.
5. **Group requirements into categories** relevant to the type of work (see below - adapt the categories to the domain, don't force a web-dev template onto a logo design job).
6. **Identify missing information** - the things a freelancer would need before they could scope, quote, or start the work.
7. **Turn the missing information into specific, answerable questions**, and mark each as **Critical** (blocks scoping or quoting) or **Nice to know** (helpful but not a blocker). Avoid vague questions like "what's your budget?" in favor of ones that give the client an easy way to answer, e.g. offering ranges or examples where it helps. Phrase these so the freelancer could copy-paste them straight into an email or message to the client - friendly and direct, not internal shorthand.
8. **Write the structured brief** using the template below.
8. **Suggest next steps** - usually 2-4 concrete actions (e.g. "send the client these questions," "propose a call to walk through payment options," "draft a rough sitemap once catalog size is known").

## Categorizing requirements

Categories should fit the type of work, not be forced into a fixed set. Some starting points:

- **Web/app development**: pages/features, content & media, technical/platform, integrations (payment, chatbot, CRM), design preferences, hosting/domain
- **Graphic design**: deliverables (formats, sizes), brand assets available, style/mood references, usage context (print vs digital)
- **Writing/content**: content types, tone/voice, length & format, target audience, SEO/keywords
- **Marketing**: channels, target audience, budget range, timeline/campaign dates, existing assets
- **General/consulting**: scope of work, deliverables, timeline, stakeholders involved

If the project spans domains (e.g. a website that also needs marketing copy), use sub-groupings rather than cramming everything into one flat list.

## Output template

Use this structure. Keep it scannable - freelancers often skim this right before a client call.

```markdown
# Project Brief: [Short project name]

## Objective
[One or two sentences on what the client is fundamentally trying to achieve]

## Requirements Identified
- [Requirement the client explicitly stated]
...(grouped under sub-headings if there are multiple categories)

## Assumptions & Implied Needs
- [Something inferred but not explicitly said - flagged so the client/freelancer can confirm or correct it]
...(omit this section if nothing was inferred)

## Missing Information
- [What's unknown, and briefly why it matters]
...

## Questions for the Client
1. **[Critical]** [Specific, answerable, client-ready question]
2. **[Nice to know]** [Specific, answerable, client-ready question]
...

## Suggested Next Steps
- [Action]
- [Action]
```

## Worked example

**Client message:** "I need a website for my clothing business. I want customers to see products, contact me, and maybe order online. I also want a chatbot."

**Output:**

```markdown
# Project Brief: Clothing E-commerce Website

## Objective
An online storefront for a clothing business that lets customers browse products, get in touch, and potentially order directly online.

## Requirements Identified
- Product catalog (browsing)
- Customer contact option
- Online ordering
- AI chatbot

## Assumptions & Implied Needs
- Product images and prices (implied by "customers see products," not stated outright)
- Some kind of catalog structure, not just a single static page

## Missing Information
- Number of products (affects catalog structure and site complexity)
- Payment method(s) the store should support
- Delivery areas / shipping policy
- Whether the site should be built on a platform like Shopify/WooCommerce or custom-built
- What the chatbot should actually do (FAQ bot? order support? styling advice?)
- Whether "maybe order online" means online ordering is required for launch or a possible phase 2

## Questions for the Client
1. **[Critical]** Roughly how many products will you be listing at launch, and do you expect that number to grow quickly?
2. **[Critical]** Which payment methods would you like customers to use - cards, PayPal, cash on delivery, something else?
3. **[Nice to know]** Do you already have product photos, or should we plan to source/shoot those?
4. **[Critical]** Which areas or countries do you deliver to?
5. **[Nice to know]** Do you already have a domain and hosting set up, or a preference for a platform like Shopify?
6. **[Critical]** For the chatbot, what would you like it to help with - answering FAQs, tracking orders, recommending products?
7. **[Critical]** Is online ordering something you need right at launch, or would browsing + contact be enough for version one?

## Suggested Next Steps
- Send these questions to the client before quoting a price or timeline
- Once catalog size and platform preference are known, draft a rough sitemap
- Clarify chatbot scope separately, since it can range from a simple FAQ widget to a much larger integration
```

## Output format: chat or file

Default to writing the brief directly in the chat response as formatted markdown - that's fastest to review and copy into an email. Create an actual downloadable file (e.g. a `.docx` via the docx skill, or a `.md` file) instead when:

- The user explicitly asks for a file, document, or something to "send" or "attach"
- The brief is long or detailed enough that it reads like a deliverable rather than a quick chat reply (e.g. a multi-service project with many categories)

If it's ambiguous, ask the user which they'd prefer rather than guessing.

## Handling partial or already-clear messages

Not every client message is a jumble. If the client's message is already fairly clear and complete, don't invent missing information for the sake of filling out every section - just note that few or no clarifying questions are needed, and say why. Conversely, if the message is extremely short (e.g. "I need a logo"), it's fine for the "Missing Information" and "Questions" sections to be the bulk of the output - that's the more useful output in that case.
