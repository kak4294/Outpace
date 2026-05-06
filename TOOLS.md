# Outpace Tooling Bible
### What every tool is, what it does, and how it fits into your pipeline

---

## How This Document Works

This is your reference guide for the entire Outpace tech stack. Each tool is broken down into: what it is in plain English, what it actually does, how it fits into the Outpace pipeline, what it costs, and what you need to do to learn it. Work through this sequentially. The tools are ordered in the same order data flows through a campaign.

---

## The Pipeline at a Glance

```
[1. FIND LEADS] --> [2. ENRICH DATA] --> [3. SEND EMAILS] --> [4. MANAGE REPLIES] --> [5. BOOK MEETINGS] --> [6. TRACK IN CRM]
   Apollo/Clay        Clay/Clearbit       Instantly/Smartlead    Instantly Unibox      Calendly/Cal.com       HubSpot/Pipedrive
```

Each tool below maps to one or more of these stages.

---

## STAGE 1: Lead Sourcing (Finding People to Email)

### Apollo.io

**What it is:** A massive database of 265M+ business contacts combined with built-in outreach tools. Think of it as a phonebook for every business professional on the planet, plus the ability to email them directly from the same platform.

**What it actually does:**
- Search for people by job title, company size, industry, location, revenue, funding stage, tech stack, and 65+ other filters
- Returns their name, email, phone number, LinkedIn profile, company info
- Has built-in email sequencing (you can send campaigns directly from Apollo)
- Tracks email opens, clicks, and replies
- Integrates with HubSpot, Salesforce, and other CRMs
- Includes intent data (signals that show a company might be actively looking to buy something)

**How it fits into Outpace:**
Apollo is your primary lead sourcing tool. When a client tells you their ICP ("we sell project management software to mid-size construction firms"), you go into Apollo, set filters for:
- Industry: Construction
- Company size: 20-200 employees
- Job title: Operations Manager, VP Operations, Owner
- Location: United States
- Revenue: $2M-$50M

Apollo spits out a list of 500+ people matching those criteria with their contact info. You export that list and feed it into your sending tool.

**What it costs:**
- Free: $0/mo, 2 active sequences, very limited credits (good for testing only)
- Basic: $49/user/mo (annual), advanced filters, 30K credits/year
- Professional: $79/user/mo (annual), unlimited sequences, US dialer, A/B testing
- Organization: $119/user/mo (annual, min 3 seats), international dialer, custom reports

**Start with:** Free tier to learn the UI. Upgrade to Basic ($49/mo) when you get your first client.

**How to learn it:**
1. Sign up for the free tier at apollo.io
2. Spend 2 hours clicking through the People and Companies search tabs
3. Build 3 fake ICPs using different filter combinations
4. Export a test list of 50 people as CSV and look at what data you get
5. Watch Apollo's own YouTube tutorials (they have a full academy)
6. Key concept to understand: "credits" -- each action (finding an email, exporting a contact) costs credits that refresh monthly

**Gotchas:**
- Email data accuracy is around 65-70%. Expect 15-25% bounce rates on unverified emails
- Shared sending infrastructure means deliverability can suffer. This is why you'll use a dedicated sending tool (Instantly) instead of Apollo's built-in sequences for actual campaigns
- Credits disappear fast once you start exporting at volume. Track your usage weekly

---

### Clay

**What it is:** A data enrichment and workflow automation platform. If Apollo is a phonebook, Clay is a research assistant that takes a name and finds everything about that person from 150+ different data sources simultaneously.

**What it actually does:**
- Connects to 150+ third-party data providers (Apollo, Clearbit, Hunter, Lusha, People Data Labs, etc.)
- "Waterfall enrichment" -- if Provider A can't find an email, it automatically tries Provider B, then C, then D. This typically boosts data coverage from ~40% to ~78%
- AI agent (Claygent) that can research companies, summarize LinkedIn profiles, find news articles, and generate personalized email copy
- Spreadsheet-like interface where each column can pull data from a different source
- Can push enriched data to your CRM or outreach tools automatically

**How it fits into Outpace:**
Clay sits between lead sourcing and email sending. You might pull a raw list from Apollo, then run it through Clay to:
- Verify and find additional email addresses the Apollo list missed
- Add company data: recent funding, hiring activity, tech stack, news mentions
- Generate personalized first lines for each prospect using AI ("Congrats on the Series B, noticed you're scaling your ops team...")
- Score leads based on multiple signals to prioritize who gets emailed first

Clay is your competitive advantage layer. Most agencies skip this step and just blast Apollo lists raw. You'll have richer data and better personalization.

**What it costs:**
- Free: 100 data credits, 500 actions/mo (enough to test, not to run campaigns)
- Launch: $185/mo (2,500 data credits, 15,000 actions)
- Growth: $495/mo (6,000 data credits, 40,000 actions, CRM sync)
- Enterprise: Custom pricing

**Start with:** Free tier to learn. Clay is expensive and powerful. Don't subscribe until you have 3+ clients funding it. Use Apollo alone for your first few campaigns.

**How to learn it:**
1. Sign up for free at clay.com
2. Upload a CSV of 20 test contacts
3. Add enrichment columns: try finding emails, company revenue, LinkedIn URLs
4. Watch Clay's University videos (they have a structured learning path)
5. Join the Clay Slack community (very active, people share workflows)
6. Key concept: "waterfall enrichment" -- understand how sequential provider lookups work
7. Key concept: "credits vs. actions" -- credits buy data, actions are platform operations. A single contact enriched through 5 providers costs 5x the credits, not 1x

**Gotchas:**
- Steep learning curve. Plan 2-3 weeks to get comfortable
- Credit costs compound fast with waterfall sequences. A fully enriched contact can cost $0.15-$1.12 in credits
- Clay is an enrichment engine, NOT a sending tool. You still need Instantly/Smartlead to actually send emails
- Requires technical thinking (conditional logic, data architecture). Your CS background is a huge advantage here

---

## STAGE 2: Email Sending & Deliverability

### Instantly.ai

**What it is:** A cold email sending platform built for high-volume outbound. Its key differentiator is unlimited email account connections on every plan, which lets you distribute sending across many mailboxes to protect deliverability.

**What it actually does:**
- Connects unlimited email accounts (Gmail, Outlook, custom domains)
- Automated email warmup: gradually builds sender reputation on new mailboxes by simulating real email activity
- Sequence builder: create multi-step email campaigns (email 1 on day 0, follow-up on day 3, etc.)
- Inbox rotation: distributes sends across all connected mailboxes automatically
- Unibox: single unified inbox to manage replies from all connected accounts in one place
- AI reply classification: automatically tags replies as "interested," "not interested," "out of office," etc.
- Built-in lead database (SuperSearch) and basic CRM (both are add-ons)
- A/B testing on subject lines and email body variants

**How it fits into Outpace:**
Instantly is your campaign execution engine. After you've sourced leads (Apollo) and enriched them (Clay), you:
1. Upload the enriched lead list to Instantly
2. Write your email sequences (or use AI to generate them)
3. Connect your warmed-up sending mailboxes
4. Launch the campaign
5. Monitor opens, replies, and bounces in the dashboard
6. Manage positive replies in Unibox and route them to the client

This is the tool you'll spend the most time in on a daily basis.

**What it costs:**
- Growth: $37/mo (1,000 active leads, 5,000 emails/mo, unlimited accounts, unlimited warmup)
- Hypergrowth: $97/mo (25,000 active leads, 100,000 emails/mo)
- Light Speed: $358/mo (100,000 active leads, 500,000 emails/mo)
- Add-ons: Lead Finder ($47-$82/mo), CRM ($47-$97/mo), Credits for AI features

**Start with:** Growth plan at $37/mo. This covers your first 1-2 client campaigns easily.

**How to learn it:**
1. Sign up for the 14-day free trial at instantly.ai
2. Connect 1-2 test email accounts and turn on warmup immediately (warmup takes 2-3 weeks to build reputation)
3. Build a test sequence with 3 emails
4. Send a small test campaign to yourself and a few friends to see the flow
5. Explore Unibox -- understand how reply management works
6. Watch Instantly Academy (600+ templates, 50 SOPs, training materials included)
7. Key concept: "inbox rotation" -- how sends are distributed across mailboxes
8. Key concept: "active leads" -- the limit on Growth plan is 1,000 contacts actively in a sequence at once, not 1,000 total ever

**Gotchas:**
- The $37/mo price is the sending tool ONLY. Add lead finder, CRM, and credits and you're quickly at $150-250/mo
- 1,000 active lead limit on Growth means you need to manage campaigns to keep completed contacts cleared out
- Advanced AI features are locked behind higher tiers or credit purchases
- Deliverability is good but not perfect. You still need proper domain/DNS setup

---

### Smartlead (Alternative to Instantly)

**What it is:** A competing cold email platform to Instantly with similar core features but stronger analytics and a white-label agency dashboard.

**How it fits into Outpace:** Direct alternative to Instantly. Many agencies use Smartlead specifically because it has better agency features (manage multiple client campaigns from one dashboard with white-label reporting).

**What it costs:**
- Basic: $39/mo (2,000 active leads, 6,000 emails)
- Pro: $94/mo (30,000 active leads, unlimited clients)
- Custom: $174/mo (unlimited active leads, unlimited clients)

**When to consider:** If you scale past 3-5 clients and need better multi-client management. For starting out, Instantly's Growth plan is cheaper and simpler.

---

## STAGE 3: Email Infrastructure (The Unsexy Critical Stuff)

### Sending Domains & Mailboxes

**What this is:** You never send cold emails from your main domain (outpace.com). You buy separate "sending domains" that look similar (like getoutpace.com or outpacehq.com) and create mailboxes on them. If a sending domain gets flagged for spam, your main domain stays clean.

**What you need to know:**
- Buy 2-3 sending domains per client campaign from Google Domains, Namecheap, or Cloudflare ($10-15/domain/year)
- Set up Google Workspace or Microsoft 365 mailboxes on each domain ($6-7/mailbox/month)
- Configure DNS records: SPF, DKIM, DMARC (these are email authentication protocols that prove you're a legitimate sender)
- Warm up each mailbox for 2-3 weeks before sending any cold emails
- Rule of thumb: send no more than 30-50 emails per mailbox per day

**How to learn it:**
1. Buy one test domain from Namecheap or Cloudflare
2. Set up Google Workspace on it
3. Configure SPF, DKIM, DMARC records (Google provides step-by-step instructions)
4. Connect the mailbox to Instantly and enable warmup
5. Key concept: "domain warming" -- a gradual ramp-up process where the warmup tool sends and receives emails between accounts in its network to build your sender reputation with Gmail/Outlook servers
6. This is DNS configuration. With your background in Nginx, systemd, and Tailscale, this will feel very familiar

### Pre-warmed Inbox Providers (Litemail, Mailforge, Maildoso)

**What these are:** Services that sell you pre-warmed Google Workspace or Microsoft 365 inboxes ready to send cold emails immediately, skipping the 2-3 week warmup period. They handle domain purchase, DNS setup, and warming for you.

**What they cost:** $4.99-$8/inbox/month

**When to use:** When you're scaling past 5+ clients and setting up individual domains/mailboxes manually becomes a time sink. For your first few clients, doing it manually teaches you the fundamentals.

---

## STAGE 4: Reply Management & Meeting Booking

### Instantly Unibox (Built into Instantly)

**What it is:** A unified inbox inside Instantly that aggregates replies from all your connected sending accounts into one view. Instead of checking 10 different Gmail accounts, you see everything in one place.

**How it fits into Outpace:** This is where you spend 10-15 minutes per day per client checking for positive replies, routing them appropriately, and making sure nothing falls through the cracks.

### Calendly / Cal.com

**What these are:** Scheduling tools that let prospects book meetings directly on a calendar. You embed a link in your emails or follow-ups.

**How they fit into Outpace:** When a prospect replies with interest, the follow-up (automated or manual) includes a Calendly/Cal.com link to book time with your client's sales rep. The meeting appears directly on the rep's calendar. No back-and-forth scheduling.

**What they cost:**
- Calendly: Free (1 event type), Standard $10/mo, Teams $16/mo
- Cal.com: Free (open source), Teams $15/mo

**Start with:** Calendly free tier or Cal.com free tier.

---

## STAGE 5: CRM Integration

### HubSpot CRM

**What it is:** A customer relationship management platform where businesses track leads, deals, and customer interactions. It's the most common CRM for small-to-mid-market B2B companies.

**How it fits into Outpace:** Most of your clients will already use HubSpot (or Salesforce, or Pipedrive). Your job is to connect Instantly to their CRM so that when a lead replies interested, a new contact/deal is created automatically in their system. Their sales rep gets notified and takes over.

**What it costs:** Free CRM (genuinely useful free tier), paid plans start at $20/mo

**How to learn it:**
1. Create a free HubSpot account
2. Add 10 fake contacts manually to understand the data model
3. Explore deals/pipeline view
4. Set up a test integration with Instantly (native integration or Zapier)
5. Key concept: "pipeline stages" -- a visual board showing where each deal is (New Lead > Contacted > Meeting Booked > Proposal Sent > Closed Won/Lost)

### Zapier / Make

**What these are:** Automation platforms that connect different tools together without code. "When X happens in Tool A, do Y in Tool B."

**How they fit into Outpace:** These are your glue. Examples:
- When Instantly tags a reply as "interested," create a new contact in HubSpot
- When a Calendly meeting is booked, update the deal stage in HubSpot and send a Slack notification to the client
- When Apollo exports a new list, add it to an Instantly campaign

**What they cost:**
- Zapier: Free (100 tasks/mo), Starter $19.99/mo, Professional $49/mo
- Make: Free (1,000 ops/mo), Core $9/mo, Pro $16/mo

**Start with:** Zapier free tier. It's more intuitive than Make for beginners.

**How to learn it:**
1. Sign up for Zapier free
2. Build a test "Zap": when you receive an email in Gmail, create a row in Google Sheets
3. Understand the trigger/action model
4. Browse Zapier's template library for Instantly + HubSpot automations

---

## STAGE 6: Analytics & Reporting (Your Differentiator)

### Your Custom Data Layer

**What this is:** This is the part YOU build. Not a third-party tool. A database and analysis pipeline that ingests campaign data from all the tools above and turns it into insights.

**How it fits into Outpace:** Every tool above has an API or CSV export. You pull campaign metrics (sends, opens, replies, bounces, meetings booked) into a central database. You run analysis on it. You generate reports for clients. Over time, this data becomes your moat.

**Recommended stack:**
- SQLite or PostgreSQL for data storage (you already know SQLite well)
- Python (pandas, scipy) for analysis
- A simple Flask dashboard or Google Sheets for client-facing reports (start with Sheets, build custom later)

**What to track from day one:**
- Open rate by subject line variant
- Reply rate by email body variant, by ICP segment, by send time, by day of week
- Bounce rate by data source (Apollo vs. Clay enriched)
- Positive reply rate by personalization depth
- Time from first email to meeting booked
- Cost per meeting booked (your tooling costs / meetings generated)

**How to learn it:** You already know how to do this. This is SQL queries, pandas DataFrames, and basic statistical analysis. The only new part is learning each tool's API or export format.

---

## Tool Spending Summary (Month 1, First Client)

| Tool | Plan | Monthly Cost |
|------|------|-------------|
| Apollo.io | Basic | $49 |
| Instantly | Growth | $37 |
| Sending domains (2-3) | Google Workspace | $20-25 |
| Domains | Namecheap/Cloudflare | $3-5 |
| Calendly | Free | $0 |
| HubSpot CRM | Free | $0 |
| Zapier | Free | $0 |
| **Total** | | **~$110-115/mo** |

If you charge a client $2,500/mo, your margins are over 95% on tooling alone. Your main cost is your time.

---

## Learning Priority Order

1. **Week 1:** Apollo (lead sourcing) + Instantly (email sending) + DNS/deliverability basics
2. **Week 2:** Build and send your first test campaign (to yourself, then to a real list)
3. **Week 3:** HubSpot CRM basics + Zapier integrations
4. **Week 4:** Clay (data enrichment) -- only after you understand the basics
5. **Ongoing:** Build your analytics/reporting layer as data comes in

---

## Key Resources

- **Cold email fundamentals:** r/coldemail subreddit, Alex Berman YouTube, Patrick Dang YouTube
- **Apollo training:** Apollo Academy (built into the platform)
- **Instantly training:** Instantly Academy (600+ templates, 50 SOPs)
- **Clay training:** Clay University + Clay Slack community
- **Deliverability:** Search "cold email deliverability guide 2026" -- there are dozens of free comprehensive guides
- **Zapier:** Zapier's own tutorial library