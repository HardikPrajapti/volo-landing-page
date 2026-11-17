# mockup7: plan (draft for approval)

Status: **planning, nothing built.** Built on mockup6's palette and content; everything new needs your yes first.

## 1. The idea in one line

Most TPA sites *say* "fast, trusted claims". mockup7 **shows one claim happening** (from the hospital desk to settlement) and **ties every logo to a real voice**. One memorable moment, everything else calm.

## 1b. Competitive research (17-11-2026)

| Competitor | Hero | Trust signals | Motion | Gap we can use |
|---|---|---|---|---|
| **Medi Assist** (largest TPA) | No clear headline or action ("Borderless Benefits") | "10M+ claims/yr", "11K enterprise clients", "INR 259B premiums"; testimonials from partner CEOs (Policybazaar, MediBuddy) | Almost none, GIF icons | Doesn't say who it's for; no member path up front |
| **MD India** | "Networking the Future of Healthcare Services"; View claim status / Download e-card | "27 CR+ lives", IRDAI No. 005; no logos or testimonials | Sliders, count-up counters | Counters show **"0"** without their script; hospital count contradicts itself (10,700 vs 19,500); 8 login portals |
| **Vidal Health** | "India's Leading Healthcare TPA"; Find a hospital / File a claim | 5 counters (show "0" without their script), IRDAI No. 016, insurer + employee testimonials | Role tabs, carousel | **Role selector** (Policyholder / Provider / Partner / HR) is good; images served from test servers |
| **Plum** (benefits startup) | "Employee benefits your team deserves" | 100K claims, 6,000 companies, awards, ISO 27001/SOC 2, logo wall (Zomato, CRED, Atlassian), HR testimonials, founders' letter | Carousels, product screens | Most polished; built for HR buyers, not members at a hospital |
| **Loop Health** | "Healthcare & insurance made easy" + Claims helpline | 1,250+ companies, 100K+ claims, 4.8 app rating, HR testimonials, case studies | Carousels, tabs | Same playbook as Plum |

**What everyone does:** a stats strip, a logo or award wall, quotes in a carousel, e-card/claim/hospital buttons, WhatsApp and app pushes.
**What nobody does:** show a claim actually moving, let a logo open its own story, give stats an "as of" date and a definition, or keep the member at the hospital desk as the first priority while still convincing HR.
**Rules we take from them:**
- Stats are real HTML numbers (never "0" before animation), all from one source, with an "as of" date.
- One login entry with clear roles (Vidal's selector idea), not 8 portals.
- No images or links pointing at test servers.

## 2. Who lands here, and what they want first

| Visitor | Arrives because | Needs within 5 seconds |
|---|---|---|
| Member (often at a hospital desk, on a phone, stressed) | Admission, e-card, claim worry | Helpline, e-card, claim status |
| HR / corporate buyer | Evaluating a TPA, renewal | Proof: which companies, how fast, who vouches |
| Insurer / broker / Policybazaar-type partner | Partnership, empanelment | Scale, compliance, TAT, partner voices |

The hero serves the member first (urgent), with one clear door for HR and partners.

## 3. Three directions (pick one)

### A. "The card": recommended
The VOLO e-card, the one object every member actually carries to a hospital, is the hero: a **3D card** that tilts with the pointer or phone. On scroll, it **travels into the claim story**: it lands on a hospital desk, a 60-minute dial starts, the stages light up, and it ends at "Settled".
- Why: it comes from the TPA's own world (not generic tech), it's instantly understandable, and the 3D has a purpose.
- Cost: medium. CSS 3D plus GSAP ScrollTrigger; no heavy WebGL. Fast on cheap phones.

### B. "The clock"
Typography-led. The hero is a big live dial: "Cashless decision in **34 min** on average" (real number needed). Scroll scrubs through a hospital stay hour by hour.
- Why: very clear, bold, data-driven.
- Cost: low. Less "wow", and no real 3D.

### C. "The network"
A 3D India (three.js) where hospitals, corporates and insurers light up as you scroll.
- Why: biggest spectacle.
- Cost: high. Needs real location data (or it's fake). Heavy on phones. Highest risk of looking like generic "AI globe" design.

## 4. Proposed section order (direction A)

```
┌ Notice bar (mockup2 pill)                                   │
├ Fixed header: logo · Members · HR · Partners · Help · [Member login] [menu]
├ 1 HERO      "Your health cover, working the moment you need it"
│             [3D e-card]   quick tasks: e-card · claim status · hospital · helpline
│             door: "Running health cover for a company? →"
├ 2 PROOF     stats strip: insurers · corporates · claims settled · 24×7 · avg TAT
├ 3 STORY     ★ signature: the card's journey, one claim scroll-told
│             admission → cashless request → decision (dial) → discharge → settled
├ 4 TRUST     logos that speak: click a corporate/insurer logo → its quote opens
├ 5 VOICES    testimonials by audience: Members │ HR │ Insurers │ Partners
├ 6 MEMBERS   self-service: app (3D phone with real screens) + portal + WhatsApp
├ 7 HR        what HR gets (PulsePoint) + "Talk to us"
├ 8 SAFE      IRDAI reg, certifications, official channels, grievance path
├ 9 HELP      claim-status lookup · FAQ · document checklist · contact
└ Footer
```

## 5. More sections you could add (my suggestions)

1. **Logos that speak** (in the order above): a logo opens its testimonial and one fact ("3,200 employees · with Volo since 2019"). Nobody in the competitor set does this.
2. **Case study cards for HR**: before/after (e.g. cashless share went from 55% to 81%). Loop uses these heavily.
3. **Our story since 2002**: East West Assist → Volo, as a short timeline. Builds continuity trust after the rename.
4. **Grievance and escalation path**: who to contact at levels 1, 2 and 3, and the IRDAI Bima Bharosa link. Strong trust signal, often required.
5. **Security and certifications**: ISO 27001, data privacy, "we never ask for OTP". Only if real.
6. **Awards and press**: only if real.
7. **Hospital finder teaser**: a city search box that opens the real network page.

## 6. Motion rules (so it never feels like AI slop)

- **One signature moment** (the card story). Every other section is calm: no fade-up on every block, no lift on every card.
- Motion answers people: the card tilts under your hand, a logo opens its quote when tapped, tabs slide.
- Counters run once and show the real value instantly with reduced motion.
- Anything that moves by itself has **pause** (WCAG 2.2.2). Reduced-motion users get a static, complete page.
- No purple/pink gradient washes, no glassmorphism, no floating blobs, no "→" on every link.
- Each animation must explain something (progress, time, cause → effect) or it goes.

## 7. Stats: what each needs before it can appear

| Stat | Needs | Note |
|---|---|---|
| Insurers | exact current count | page said 23 but shows 10 logos |
| Corporates | exact count | |
| Claims processed / settled | number + period + definition | settled ≠ processed; pick one |
| 24×7 | which channels are really 24×7 | helpline? WhatsApp? cashless desk? |
| Cashless approval | **our actual average** | "under 60 min" is now IRDAI's legal minimum, so it doesn't differentiate |
| Average TAT | cashless vs reimbursement, from what event to what event | e.g. "reimbursement: documents complete → paid" |

All stats get an "as of" date (trust + accuracy).

## 8. Testimonials: rules

- Four audiences: **members, HR/corporates, insurers, distribution partners (e.g. Policybazaar)**.
- Real name, role and company (members may use first name + city), with written consent.
- Until real quotes arrive, the mockup shows clearly labelled placeholders ("Sample, awaiting real quote"). **No made-up quotes presented as real.**

## 9. Tech (single HTML file, like the earlier mockups)

- CSS 3D transforms for the card and phone; GSAP plus ScrollTrigger from a CDN for the scroll story.
- three.js only if direction C is chosen.
- Same quality bar as mockup6: 320–1440 px, keyboard, axe clean, reduced motion, mobile header checks.
- A new `Double-Check-mockup7.md` carries over the open items.
