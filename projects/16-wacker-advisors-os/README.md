# Wacker Advisors OS

**Status:** 🔄 Active  
**Started:** Mar 2026  

## What This Is

Full AI-powered operating system for a one-man outsourced CFO/CCO/COO advisory firm
serving emerging fund managers. Every workflow automated or AI-assisted: client onboarding,
compliance calendar management, deliverable tracking, invoice generation, engagement
letters, and quarterly reports. Infrastructure is production-ready.

## Architecture

- **Automation stack:** Typeform → Airtable → Zapier → DocuSign → Google Drive
- **AI layer:** Claude skills for every document type and advisory function
- **Document suite:** NDA, Service Agreement, Named Officer Addendum — pre-filled from
  intake data, DocuSign-ready
- **Compliance layer:** Regulatory deadline tracking, Form ADV reminders, SEC filing
  calendar
- **Financial layer:** QuickBooks Online integration, automated invoicing on 1st of month

**Claude skills deployed:**
- Root `CLAUDE.md` operating layer — full COO/CFO operations with persistent context
  files, auto-loaded every session (replaced the `pch-advisory` master skill May 2026
  after skills proved to under-trigger)
- `regpartner` — SEC compliance expert (Form ADV, Form PF, Marketing Rule, Custody Rule)
- `invcogaap` — ASC 946 investment company accounting
- `website-copy` — brand voice-compliant public content
- `resume-builder` — tailored resume generation

**Design principle:** Zero-touch where possible, one-touch for exceptions. Peter reviews
and approves; the system executes.

## Key Decisions

**Build the OS before the client load.** Infrastructure built under pressure gets built
wrong. Every workflow, document, and automation is designed at full quality before the
first client signs. The first engagement runs on a production system, not a prototype.

**Persistent context files over re-explaining every session.** Every Claude skill reads
current business state from context files at session start. This means a new session
doesn't require re-establishing context — the AI already knows the business, the client
roster, the current OKRs, and the active constraints.

**"I" not "we" throughout all client-facing materials.** Solo practitioner reality is a
competitive advantage: clients get the principal directly, always. No hand-offs to
associates. The marketing and documents reflect this explicitly.

**Compliance calendar as the backbone.** For fund manager clients, missing a regulatory
deadline is catastrophic. The compliance calendar is automated with 60-day advance
alerts and is the first thing built for every new client engagement.

## Current Milestone

Repositioned May 28, 2026: the firm is now an AI-native fractional CFO + CCO practice
serving four client profiles — emerging fund managers and family offices, independent
sponsors and search funds, PE/VC portfolio companies, and owner-operated private
businesses. The v2 website shell reflecting the new positioning was built June 1;
publishing it is the gate to first-client outreach (target July 2026).

## Lessons Learned

The highest-leverage investment in a one-person firm is the operating system — not the
work product. Well-structured systems mean each additional client adds less marginal
time than the last. Poorly structured systems mean each client adds a full linear load.

Building the skills first, before client pressure created shortcuts, produced a
significantly better result. The discipline to build the right foundation before
generating revenue is the difference between a practice that compounds and a busy job.

---

*Part of the [Claude Architect Journey](../../README.md)*
