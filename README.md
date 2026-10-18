# AI-Ready BA landing page

Lead-capture page for the free report *The AI-Ready Business Analyst* from Business Analyst Services. It is a static site: one `index.html`, plus logos in `assets/`. There is no build step. 

## Deploy

1. Push this folder to a new GitHub repository, for example `bas-ai-ready-ba`.
2. In Vercel, choose **Add New → Project**, import the repository, set **Framework Preset** to *Other* and leave the build settings empty.
3. Under **Settings → Domains**, add the subdomain (for example `learn.business-analyst.services`), then add the CNAME record Vercel shows at your DNS provider.

## Connect the form to GoHighLevel

1. In GoHighLevel, create a workflow with the trigger **Inbound Webhook** and copy its URL.
2. In `index.html`, paste that URL into `var GHL_WEBHOOK_URL = ''`.
3. In the workflow, map the fields `first_name`, `email`, `segment` and the `utm_*` fields; add the tag from `segment` (`seg-ba`, `seg-lead` or `seg-gov`); start the nurture sequence (email 1 delivers the report).
4. Submit a test lead and check that the contact appears in GHL.

Until the webhook URL is set, the form shows the thank-you message but **does not save the lead**.

## Tracking

Paste the GA4, LinkedIn Insight Tag and Meta Pixel snippets just before `</head>`. The form fires a GA4 `generate_lead` event when `gtag` is present.

## Brand

Styles follow the BAS design system: navy `#1F3A5F`, teal `#4DB8B8`, orange `#F5A04A` for the call to action only, Arial, square corners, teal eyebrows, two-line headlines and a teal footer band.

## Links

- Booking: https://calendar.app.google/Mrs8mmZiXxxb3pta6
