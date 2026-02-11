# WCAG Development Process Research

How the WCAG specification was developed — process, not content. Practical insights for building a new specification from scratch.

## Status: Complete

---

## 1. Development Timelines

### WCAG 1.0 (2 years)

| Date | Milestone |
|------|-----------|
| August 1997 | WCAG Working Group chartered within WAI |
| February 1998 | First Public Draft |
| May 5, 1999 | W3C Recommendation (final) |

**Total: ~20 months from first draft to final.** This was a relatively short development cycle. WCAG 1.0 was 14 guidelines with 65 checkpoints, tightly focused on HTML. The scope was narrow and the web was young — both factors that kept the timeline manageable.

**Pre-history:** Gregg Vanderheiden compiled the first web accessibility guideline in January 1995. The "Unified Web Site Accessibility Guidelines" went through 8 versions by 1998 and served as the starting point for WCAG 1.0. So the intellectual foundation was ~4 years of prior work before the formal W3C process began.

### WCAG 2.0 (7+ years)

| Date | Milestone |
|------|-----------|
| January 25, 2001 | First Working Draft |
| August 24, 2001 | Working Draft |
| August 22, 2002 | Working Draft |
| April 29, 2003 | Working Draft |
| June 24, 2003 | Working Draft |
| March 11, 2004 | Working Draft |
| July 30, 2004 | Working Draft |
| November 19, 2004 | Working Draft |
| June 30, 2005 | Working Draft |
| November 23, 2005 | Working Draft |
| April 27, 2006 | Last Call Working Draft (1st) |
| May 17, 2007 | Working Draft (reset after too many amendments) |
| December 11, 2007 | Last Call Working Draft (2nd) |
| April 30, 2008 | Candidate Recommendation |
| November 3, 2008 | Proposed Recommendation |
| December 11, 2008 | W3C Recommendation (final) |

**Total: ~8 years from first draft to final.** 12 Working Drafts, 2 Last Call drafts, 16 publications total. Over 3,000 comments addressed.

**Why it took so long:** The scope expanded massively — WCAG 2.0 attempted to be technology-neutral (not just HTML) and future-proof. This abstraction created enormous complexity in making criteria both testable and comprehensible. The 2006 Last Call generated so many amendments they had to reset to a new Working Draft, adding ~2 years.

### WCAG 2.1 (18 months)

| Date | Milestone |
|------|-----------|
| February 2017 | First Public Working Draft |
| January 30, 2018 | Candidate Recommendation |
| April 24, 2018 | Proposed Recommendation |
| June 5, 2018 | W3C Recommendation (final) |

**Total: ~16 months from first draft to final.** This was fast because WCAG 2.1 was explicitly an increment — 17 new success criteria added to WCAG 2.0 without changing existing ones. The backward-compatible constraint dramatically reduced scope and controversy.

### WCAG 2.2 (~3.5 years, with delays)

| Date | Milestone |
|------|-----------|
| February 2020 | First Public Working Draft |
| September 2022 | Candidate Recommendation |
| May 2023 | Proposed Recommendation |
| October 5, 2023 | W3C Recommendation (final) |

**Total: ~3.5 years.** Originally targeted for much earlier, WCAG 2.2 was delayed over a year. Nine new success criteria were added and one was removed (4.1.1 Parsing). The delays stemmed from disagreements about specific criteria and real-world implementation testing.

### WCAG 3.0 (ongoing, 10+ years projected)

| Date | Milestone |
|------|-----------|
| 2016 | Silver Task Force established |
| Late 2016 - Early 2018 | 16 months of research |
| March 2018 | Design Sprint with 27 industry leaders |
| January 2021 | First Public Working Draft |
| 2027 (projected) | Draft Candidate Recommendation |
| 2028+ (projected) | Final Recommendation (earliest) |

**Projected total: 12+ years from task force to final.** WCAG 3.0 is a fundamental restructuring, not an increment. The group spent their first years doing research on what went wrong with WCAG 2.x before writing any spec text.

### Timeline Lessons

| Version | Duration | Scope Strategy |
|---------|----------|----------------|
| 1.0 | ~2 years | Narrow scope, HTML-specific |
| 2.0 | ~8 years | Ambitious scope expansion, technology-neutral |
| 2.1 | ~16 months | Strict increment, backward-compatible |
| 2.2 | ~3.5 years | Increment with scope debates |
| 3.0 | 12+ years | Fundamental restructuring |

**Key insight:** Narrow scope and backward-compatible increments ship fast. Ambitious rewrites take a decade. If OOS wants to ship, start extremely narrow (L1) and iterate.

---

## 2. Working Group Structure

### How the W3C WAI Working Group Was Organized

The Web Content Accessibility Guidelines Working Group (WCAG WG, later renamed Accessibility Guidelines Working Group / AG WG) operates within the W3C's Web Accessibility Initiative (WAI).

**Participant composition:**
- Expected 15+ active participants (recent charters relaxed this to 6+)
- Representatives from key implementors (browser vendors, assistive technology makers)
- Active Editors and Test Leads for each specification
- Mix of corporate representatives, disability advocates, researchers, and independent experts
- Participants from organizations like IBM, Oracle, SAP, Adobe, Google, Microsoft, accessibility consultancies

**Leadership:**
- Chairs (typically 2-3 co-chairs) responsible for running meetings, determining consensus, managing process
- W3C Staff Contact providing process guidance and coordination
- Specification Editors doing the actual writing
- Test Leads managing conformance testing

**Time commitment:**
- Chairs, Editors, and Test Leads: ~half a working day per week
- Other participants: no formal minimum, but expected to keep up with weekly work
- Conference calls: typically weekly, 1-2 hours
- Face-to-face meetings: 1-2 per year (at TPAC and sometimes CSUN)

**Task Forces (specialized subgroups):**
- Cognitive and Learning Disabilities Task Force
- Low Vision Accessibility Task Force
- Mobile Accessibility Task Force
- Accessibility Conformance Testing Task Force
- WCAG2ICT Task Force (applying WCAG to non-web ICT)
- WCAG 2.x Backlog Task Force
- Silver Task Force (WCAG 3.0 development)

**WCAG 3.0 subgroup model (new approach):**
- Small temporary groups of 4-6 members
- Each has a facilitator
- Work for ~8 weeks on a specific proposal
- Report back to full working group for consensus
- Agile-inspired: iterate quickly, get feedback, refine

### Participation Requirements

To join the AG WG formally, you need to either:
1. Be employed by a W3C Member organization (your employer pays W3C membership fees)
2. Be invited as an "Invited Expert" (no fee, but requires approval)

Non-members can still:
- Comment on public drafts
- File GitHub issues
- Participate in Community Groups
- Attend public events

### What This Means for OOS

The W3C Working Group model requires significant organizational infrastructure. For OOS, the Community Group path or independent development is more realistic at the start. The task force / subgroup model is worth emulating — small teams tackling specific problems and reporting to the larger group.

---

## 3. Drafting Process: From Principles to Success Criteria

### WCAG 2.0 Approach

**Step 1: Establish principles.** The four POUR principles (Perceivable, Operable, Understandable, Robust) were established early as an organizing framework. These are high-level, stable, and rarely controversial.

**Step 2: Define guidelines under principles.** Each principle got 3-4 guidelines — more specific but still goal-oriented rather than testable.

**Step 3: Write testable success criteria.** This is where the real work happened. Each guideline needed specific, testable criteria at three conformance levels. The working group iterated extensively on:
- Can this be tested reliably?
- Is this technology-neutral?
- Is this the right conformance level?
- Does this place an unreasonable burden on authors?

**Step 4: Develop techniques separately.** Techniques (how to meet criteria) were published as separate, informative (non-normative) documents. This was a deliberate design decision — the spec says *what* to achieve, techniques say *how*, and techniques can be updated without changing the spec.

**Step 5: Write "Understanding" documents.** Each success criterion got an explanatory document covering intent, benefits, examples, and related resources. These helped bridge the gap between abstract criteria and practical implementation.

### The Iteration Process

WCAG 2.0's development was marked by extensive iteration:

1. **Internal drafts** — Editors produce proposals, working group discusses
2. **Working Drafts** — Published for broader review (12 WDs for WCAG 2.0)
3. **Last Call Working Draft** — Signal that the group believes the spec is ready; formal comment period
4. **Candidate Recommendation** — Spec is stable; implementers test it; at least 2 independent implementations needed
5. **Proposed Recommendation** — W3C Advisory Committee votes
6. **Recommendation** — Final standard

At each stage, comments trigger revisions. The 2006 Last Call for WCAG 2.0 generated so many comments that the group had to fall back to Working Draft status and try again — a full reset that added 2 years.

### WCAG 3.0 Process Changes

Learning from WCAG 2.0's struggles, WCAG 3.0 adopted a different drafting approach:

1. **Research first** — 16 months of research before writing any spec text
2. **Design sprint** — 27 industry leaders, agile techniques, 2018
3. **Subgroup model** — 4-6 people, 8-week sprints, specific proposals
4. **Maturity levels for content** — Individual sections can be at different maturity levels (Placeholder, Exploratory, Developing, Refining, Mature)
5. **Iterative publication** — Publish early, update sections independently

---

## 4. Public Review Process

### How WCAG Handled Public Feedback

**Scale:** WCAG 2.0 received over 3,000 comments across its 12 Working Drafts and 2 Last Call periods.

**Comment collection methods:**
- Online comment form (preferred)
- Public mailing list (public-comments-wcag20@w3.org)
- All comments publicly archived
- GitHub issues (for later versions)

**Formal review stages in the W3C process:**

| Stage | Duration | Purpose |
|-------|----------|---------|
| Working Draft | Ongoing | Informal feedback welcome |
| Last Call Working Draft | Defined period (e.g., 34 days for WCAG 2.0) | Formal comment period; group must respond to every comment |
| Candidate Recommendation | Variable | Implementation feedback |
| Proposed Recommendation | ~4 weeks | W3C Advisory Committee review |

**Comment disposition:**
- Every Last Call comment must receive a formal response
- The working group publishes a "Disposition of Comments" document showing each comment and how it was addressed
- Categories: Accepted, Partially Accepted, Rejected (with rationale), Deferred
- Commenters can escalate unresolved issues as Formal Objections

**Problems with the review process:**
- The WCAG 2.0 first Last Call gave only 34 days for public comment on a document that took 5 years to develop — widely criticized as insufficient
- Volume of comments (3,000+) overwhelmed the working group
- Power dynamics favored "multinationals with expense accounts" who could participate in weekly calls
- Non-English speakers effectively excluded from the process
- People with disabilities themselves faced accessibility barriers in participating (deaf participants couldn't access conference calls; people with cognitive disabilities struggled with dense spec language)

### What This Means for OOS

- Plan for multiple review stages with adequate time
- Use GitHub issues for public comment (modern, accessible, threaded)
- Publish formal responses to all substantive comments
- Actively solicit feedback from diverse stakeholders, not just those who show up
- Keep the spec readable enough that your target audience can actually review it

---

## 5. Consensus Building

### The W3C Consensus Model

Consensus in W3C is explicitly *not* a vote. It means "a substantial number of individuals in the group support the decision and nobody registers a Formal Objection."

**The AG Working Group's decision workflow:**

1. **Discussion phase** — All viewpoints expressed (days to weeks)
2. **Call for Consensus (CFC)** — Minimum 4 working days for non-mature content; 2 days for mature normative text
3. **Evaluation** — No objections = formal decision; substantive objections reopen discussion
4. **Recording** — All decisions documented on the AG Decisions wiki page

**For developing vs. mature content:**
- Developing content: "Broad consensus only" — questions captured as editor's notes, not formal objections
- Mature content: "Strive for unanimous agreement" — full consensus required

**When disagreements arise:**
1. Chair determines if all viewpoints have been heard
2. If consensus cannot be reached, Chair may record a decision with noted dissent
3. Objections must have "clear rationale based on technical merit"
4. Objections without substantive arguments are unlikely to receive serious consideration
5. Serious objections trigger formal minority view documentation

**Formal Objections (nuclear option):**
1. Participant registers formal objection with the Chair
2. Must cite technical arguments and propose changes
3. W3C Team attempts mediation
4. If unresolved, W3C Team prepares analysis report
5. W3C Council (formerly the Director) makes final ruling
6. Council decision includes rationale and may include guidance

**Real-world dysfunction:**
Joe Clark's 2006 criticism documented that the WCAG 2.0 working group was "the worst committee, group, company, or organization I've ever worked with." Participants reported being "ignored; threatened with ejection... and actively harassed." This created a "climate of fear" that suppressed dissent rather than building genuine consensus. Corporate participants from IBM, Oracle, and SAP had outsized influence, and the fixation on automated testing was partly driven by testing tool vendors on the committee.

### What This Means for OOS

- Define a clear decision-making process early — before there are disagreements
- Consensus does not mean unanimity; it means no one objects strongly enough to block
- Document all decisions with rationale
- Watch for power dynamics — corporate interests can distort consensus
- Keep the group small enough for genuine discussion
- Have a clear escalation path when consensus fails

---

## 6. The W3C Community Group Path

### Why This Matters for OOS

A W3C Community Group is the lightweight entry point for developing a new specification. No membership fees, no formal working group charter, no Advisory Committee overhead. It is the recommended starting point for new work that might eventually become a W3C standard.

### How to Start a Community Group

1. **Propose the group** at https://www.w3.org/community/ — provide a name and description
2. **Get 5 supporters** — five individuals must support the proposal
3. **W3C announces creation** — the Community Development Lead may reject frivolous or overly broad proposals
4. **Start working** — tools provided include mailing lists, wikis, and blogs

**Requirements:**
- No fee to create or join
- No W3C membership required
- Open to anyone
- Must have at least one Chair

**What Community Groups can produce:**
- Specifications (called "Community Group Reports" or "Final Specifications")
- Test suites
- Tutorials and demos
- Code and reference implementations
- Discussion and analysis

**What Community Groups cannot do:**
- Produce W3C Recommendations (formal standards)
- Use W3C's formal patent policy (they use the lighter CLA instead)
- Claim W3C endorsement of their work

### IP/Patent Policy

Participants sign the **Community Contributor License Agreement (CLA)**:
- Contributors license Essential Claims under RF (Royalty-Free) terms
- Covers claims they own or have right to license
- Less formal than the full W3C Patent Policy
- For "Final Specifications," the **Final Specification Agreement (FSA)** provides stronger IP commitments

### Governance

- Each group needs at least one Chair
- Groups may adopt their own operational charter (scope, decision-making, communications)
- W3C "encourages groups to adopt decision-making policies that promote consensus"
- Groups continue indefinitely until closed for inactivity or by Chair request
- The Community Development Lead can close groups for serious process violations

### Transitioning to a Full Working Group

When a Community Group spec matures enough for the standards track:

1. **Assess readiness** against W3C Recommendation Track Readiness Best Practices
2. **Identify target Working Group** — existing or new
3. **Document community support** for the transition
4. **Secure IPR commitments** — contributors can join the WG, sign a non-participant licensing agreement, or commit via the FSA
5. **Plan participant continuity** — CG members can continue as W3C members, AC representatives, or Invited Experts
6. **Handle repository transition** — typically move to W3C's GitHub organization

**Successful transitions (precedents):**
- **Decentralized Identifiers (DIDs):** Credentials Community Group developed the spec, shipped in multiple production systems, then transitioned to a formal DID Working Group
- **EPUB 3:** W3C EPUB 3 Community Group published EPUB 3.2 as a Final Specification, work continued in a formal Working Group
- **Solid Protocol:** Solid Community Group incubated specs since 2018, adopted by the Linked Web Storage Working Group

### The Silver Task Force Model (hybrid)

WCAG 3.0 uses a hybrid approach worth noting:
- The **Silver Task Force** is part of the formal AG Working Group
- The **Silver Community Group** was created alongside it for broader public participation
- Both groups share resources (mailing lists, calls, development space)
- They operate "on equal footing"

This hybrid model lets the formal standards machinery continue while opening participation to non-members through the Community Group.

### Other Options Outside W3C

Not all specs need W3C at all:
- **WHATWG** — Living standards for HTML, DOM, etc. (maintained by browser vendors)
- **IETF** — Internet standards (RFCs)
- **ECMA** — JavaScript/ECMAScript
- **Schema.org** — Vocabulary standards (independent, backed by Google/Microsoft/Yahoo/Yandex)
- **Creative Commons** — License standards (independent nonprofit)
- **Independent publication** — Many successful specs are simply published by their authors and gain adoption through utility

**For OOS specifically:** Starting as an independent specification published on openorigin.dev, with a GitHub-based development process, is perfectly viable. A W3C Community Group could come later when there is community interest and momentum. Creative Commons is a good precedent — they built a successful standard without W3C involvement.

---

## 7. Lessons Learned: What Went Wrong and What Would They Do Differently

### WCAG 2.0's Hard Lessons

**1. Scope creep killed the timeline.**
WCAG 1.0 was HTML-specific and shipped in 2 years. WCAG 2.0 tried to be technology-neutral and took 8 years. The abstraction required to support "all web technologies" made every criterion harder to write, harder to understand, and harder to agree on.

*OOS lesson:* Start technology-specific (HTML meta tags, JSON-LD). Generalize later. Ship the simple version first.

**2. The spec became unreadable.**
In Joe Clark's words: "the fundamentals of WCAG 2.0 are nearly impossible for a working standards-compliant developer to understand." Terms like "authored units" and "web units" replaced concrete language like "pages" and "sites." The group prioritized theoretical completeness over practical comprehension.

*OOS lesson:* Write for web developers, not standards lawyers. If a developer cannot read the spec and implement it without a guide, the spec has failed.

**3. Automated testing fixation distorted the criteria.**
Members of the working group who authored automated testing tools pushed for machine-testable criteria. This led to criteria that were easy to test but did not address real accessibility needs — particularly for cognitive and learning disabilities, which resist binary pass/fail testing.

*OOS lesson:* Testability matters, but do not let testing tools drive spec design. Some criteria are inherently human-judgment-dependent, and that is fine.

**4. The working group was not itself accessible.**
The accessibility standards body had accessibility problems:
- Deaf participants could not access conference calls
- Non-English speakers were excluded
- People with cognitive disabilities could not parse the dense spec language
- The participation model favored corporations with travel budgets

*OOS lesson:* Practice what you preach. If OOS is about transparency, its own development process must be transparent and accessible.

**5. Corporate capture distorted priorities.**
Large software companies (IBM, Oracle, SAP) had outsized influence. Their priorities (enterprise compliance tools, automated testing) shaped the spec more than the needs of individual developers or people with disabilities.

*OOS lesson:* Guard against capture by any single constituency. Publishers, platform vendors, and content creators all have legitimate but different interests.

**6. The public review period was too short.**
34 days for public comment on a document that took 5 years to develop. This was widely criticized. Many substantive comments arrived too late or were inadequately addressed.

*OOS lesson:* Give meaningful review time. Multiple shorter review periods are better than one long one. Publish early and often.

**7. Comments overwhelmed the process.**
3,000+ comments is a lot. The working group spent years just processing feedback. The formal requirement to respond to every Last Call comment created enormous administrative burden.

*OOS lesson:* Use GitHub issues instead of email-based comment systems. Triage aggressively. Not every comment needs a formal response — many can be grouped and addressed thematically.

### WCAG 3.0's Process Improvements

Having learned from WCAG 2.0, the WCAG 3.0 team made deliberate changes:

1. **Research before writing** — 16 months of research before any spec text. They studied what went wrong with 2.x systematically.

2. **Small subgroups** — 4-6 people, 8-week sprints, specific deliverables. This avoids the "committee of 50 trying to wordsmith" problem.

3. **Maturity levels per section** — Not all parts of the spec need to be at the same maturity. Sections can be Placeholder, Exploratory, Developing, Refining, or Mature. This allows progress on some areas while others are still being researched.

4. **Agile-inspired iteration** — Publish frequently, gather feedback, iterate. No more 5-year development cycles between public drafts.

5. **Parallel Community Group** — The Silver Community Group operates alongside the formal Task Force, opening participation without the overhead of W3C membership.

6. **Moving beyond pass/fail** — Acknowledging that some accessibility aspects cannot be reduced to binary test results. Exploring rubrics, sliding scales, and task-completion measures.

---

## Summary: Practical Advice for OOS

### Phase 1: Independent Development (Now)

1. Write the spec in plain language for web developers
2. Develop on GitHub with public issues and pull requests
3. Create reference implementations alongside the spec (dogfood on peabod.com)
4. Keep scope extremely narrow — L1 should be one meta tag
5. Publish early working drafts and invite feedback
6. Document all decisions with rationale

### Phase 2: Community Building

1. Blog about the spec, present at conferences, engage developers
2. Build validator tools that make conformance easy
3. Get 2-3 publishers to implement as proof of concept
4. Consider forming a W3C Community Group when there are 5+ interested contributors
5. Keep the spec readable — if developers need a guide to understand it, simplify

### Phase 3: Formalization (if/when needed)

1. A W3C Community Group can publish a "Final Specification" with IP protections
2. If the spec gains traction, consider transitioning to a W3C Working Group
3. Or follow the Schema.org / Creative Commons model — successful specs without W3C
4. Adoption matters more than formal standardization status

### Process Anti-Patterns to Avoid

- Do not try to boil the ocean (WCAG 2.0's technology-neutral ambition)
- Do not let the review period be too short or too long
- Do not let tooling vendors drive spec design
- Do not make the spec unreadable in pursuit of precision
- Do not require unanimity — require "no strong objections"
- Do not develop in private for years before publishing

### Process Patterns to Follow

- WCAG 2.1's incremental approach (add to existing, do not rewrite)
- WCAG 3.0's research-first approach (understand the problem before solving it)
- WCAG 3.0's subgroup model (small teams, time-boxed, specific deliverables)
- WCAG 3.0's maturity levels (not everything needs to be ready at once)
- Creative Commons' three-layer model (human-readable, machine-readable, legal)
- Schema.org's grassroots adoption model (utility drives adoption, not formal standards status)

---

## Sources

- [WCAG 2 Overview - W3C WAI](https://www.w3.org/WAI/standards-guidelines/wcag/)
- [WCAG 3 Introduction - W3C WAI](https://www.w3.org/WAI/standards-guidelines/wcag/wcag3-intro/)
- [WCAG 3 Timeline - W3C WAI](https://www.w3.org/WAI/GL/wiki/WCAG_3_Timeline)
- [WCAG 2.1 Timeline Details - W3C WAI](https://www.w3.org/WAI/GL/wiki/WCAG_2.1_timeline/Details)
- [WCAG 2.0 Publication History - W3C](https://www.w3.org/standards/history/WCAG20/)
- [AG Working Group - W3C WAI](https://www.w3.org/WAI/about/groups/agwg/)
- [AG Working Group Decision Policy - W3C WAI](https://www.w3.org/WAI/about/groups/agwg/decision-policy/)
- [AG Working Group Charter - W3C WAI](https://www.w3.org/WAI/GL/charter)
- [First Public Working Draft of WCAG 3.0: A Brief History - Deque](https://www.deque.com/blog/public-working-draft-wcag-3-history/)
- [Requirements for WCAG 3.0 - W3C](https://w3c.github.io/silver/requirements/)
- [Welcome to Silver - W3C WAI](https://www.w3.org/WAI/GL/task-forces/silver/wiki/Welcome_to_Silver)
- [To Hell with WCAG 2 - A List Apart](https://alistapart.com/article/tohellwithwcag2/)
- [Summary of Issues and Revisions on WCAG 2.0 Working Drafts - W3C](https://www.w3.org/WAI/GL/2007/12/change-summary.html)
- [W3C Community and Business Group Process](https://www.w3.org/community/about/process/)
- [How to Transition from CG to WG - W3C Guide](https://www.w3.org/Guide/process/cg-transition.html)
- [W3C Community CLA](https://www.w3.org/community/about/process/cla/)
- [W3C Patent and Copyright Policy Summary](https://www.w3.org/community/about/process/summary/)
- [W3C Formal Objections and Council](https://www.w3.org/guide/council/council.html)
- [History of WCAG - Bureau of Internet Accessibility](https://www.boia.org/blog/history-of-the-web-content-accessibility-guidelines-wcag)
- [WCAG Version History - Accessible Web](https://accessibleweb.com/wcag/wcag-version-history/)
