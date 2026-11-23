---
name: product-deconstructor
description: Automatically perform deep, evidence-based teardowns when the user gives a short request such as “teardown Spotify”, “analyse YouTube”, or “reverse-engineer Airbnb”. Infer sensible scope and independently investigate product experience, user sentiment, funnel friction, drop-off risks, retention, business model, economics, growth, competition, gaps, and technical architecture. Identify how the product could be improved and how a competitor could differentiate. Investigate backend systems, data models, APIs, search and recommendation systems, AI/ML, infrastructure, security, reliability, and engineering trade-offs where relevant. Optionally reconstruct the product into a detailed PRD and technical blueprint. Produces a structured DOCX report by default.
---

# Product Deconstructor

**Version:** 2.2.0

## Purpose

Reverse-engineer digital products from the user experience through to the business and technical systems that make them work.

The skill must explain more than what a product does. It should investigate:

1. **Experience:** What users see, do, need, and struggle with.
2. **Product:** Why capabilities exist, which problems they solve, and how they create user value.
3. **Business:** How the product acquires users, operates, captures value, and sustains itself.
4. **Technology:** What systems, data, integrations, and engineering capabilities enable the experience.
5. **Strategy:** Where the product is strong, where it is vulnerable, and what opportunities follow from the evidence.

It can also perform a second-stage **reconstruction**: turn the teardown into a proposed product strategy, MVP, PRD, user journeys, architecture, data model, APIs, roadmap, and measurement plan.

The skill is self-contained. All operating instructions live in this `SKILL.md`. Do not require separate `references/`, `templates/`, `examples/`, or `evals/` folders.

## Default behaviour

- Analyse digital products by default: marketplaces, SaaS, social networks, consumer apps, e-commerce, fintech, AI products, developer tools, platforms, and other software-led businesses.
- Default analysis depth: **Comprehensive**, including when the user provides only a short product name or a phrase such as “teardown [product]”.
- Default audience: product, business, and technical readers.
- Default deliverable for substantial work: a polished **DOCX report**.
- Give the user a concise summary in chat and save the detailed analysis in the DOCX.
- Do not dump a long report into chat when a DOCX is the better deliverable.
- If the user asks a focused question, wants a short answer, or explicitly requests chat-only output, answer directly without generating a large document.
- Always include a diagnosis of product gaps, user friction, improvement opportunities, and competitive openings. Treat full reconstruction (PRD, detailed build blueprint, implementation plan) as optional and do not produce it unless the user asks for it or clearly requests both teardown and reconstruction.
- Ask only for missing information that materially changes the analysis. If the product is clear, begin. Do not burden the user with a long questionnaire.
- If the requested product is ambiguous, ask one direct clarification.
- If the user specifies a product, geography, customer segment, timeframe, or competitor set, preserve those constraints.
- Do not assume that a product's public-facing feature set reveals its internal architecture or economics.

## Short-prompt autonomy and default interpretation

This skill is designed for real users who will usually provide short prompts, not detailed research briefs. A prompt such as **“teardown Spotify”**, **“do a teardown of YouTube”**, **“analyse Notion”**, or **“reverse-engineer Airbnb”** is sufficient to trigger the full default workflow. Do not ask the user to restate the detailed checklist already defined in this skill. The skill, not the user, is responsible for turning a short request into a rigorous investigation.

When the user gives only a product name or a short teardown request, apply these defaults:

- **Task:** Comprehensive product teardown, not merely a company overview or feature summary.
- **Subject:** Identify the most recognisable current product associated with the name. If the company has multiple products, focus on its flagship/core product and briefly state the scope chosen.
- **Geography:** Global product and business view, with important market-specific differences called out where evidence supports them.
- **Users:** Cover the main user groups and roles relevant to the product category. Do not assume a single persona.
- **Timeframe:** Current product and business state as of the research date, with historical context only where it explains a strategic or product decision.
- **Depth:** Comprehensive by default. Use Exhaustive only when explicitly requested or justified by the decision context.
- **Deliverable:** A structured, standalone DOCX for a substantive teardown, plus a concise chat summary.
- **Critical lens:** Explain what users value, what frustrates them, where journeys may fail, what the product does poorly, where competitors are stronger, and where a new or existing competitor could win.
- **Technology:** Include a substantive, product-specific technical teardown. Do not wait for the user to explicitly request “tech details”.
- **Recommendations:** Always include evidence-based product improvement opportunities and competitive openings as part of the teardown. This is analysis, not a full reconstruction.

Do not ask for audience, geography, depth, output format, competitor list, or preferred technical stack when sensible defaults are sufficient. State assumptions briefly in the report and proceed. Ask a clarification only when the product identity itself is genuinely ambiguous or when two plausible interpretations would lead to materially different work. If a product name refers to a broad ecosystem (for example, a platform with several distinct products), choose the core consumer or flagship experience, define the boundary, and mention adjacent products only where they materially affect the analysis.

The short prompt does not reduce the expected quality or scope. Never interpret “teardown Spotify” as permission to produce a shallow overview. It means: apply the complete Comprehensive teardown workflow to Spotify without requiring the user to enumerate the sections.

### Teardown versus reconstruction

A teardown must always diagnose improvement opportunities and explain how the product could be stronger. It should identify user problems, product gaps, competitive vulnerabilities, and potential differentiation. However, do not automatically produce a complete competing-product PRD, implementation plan, or build specification unless the user asks to build, recreate, clone, replace, or design a competitor. In short: **recommend how to win by default; design the full product to win only when requested.**

## Modes

Select the mode based on the user's request. If unspecified, use Comprehensive.

### 1. Focused
Use when the user asks a narrow question or wants a quick teardown.

- Focus on the relevant dimensions only.
- Avoid forcing every section into the output.
- Explain the most important evidence, implications, and uncertainties.
- Usually answer in chat or create a short DOCX only if useful.

### 2. Comprehensive (default)
Use for a serious product teardown.

- Cover all material product, business, operational, and technical dimensions in this skill.
- Treat technology as a substantive analysis section. For software products, include system context, backend capability map, data architecture, APIs/integrations, critical workflow traces, and relevant search/ML/infrastructure/reliability/security analysis.
- Adapt depth to the product category and available evidence. Do not omit a material dimension merely because public implementation detail is limited; use a clearly labelled reference design.
- Include structured tables, workflow diagrams, architecture diagrams, and data models where they improve understanding.
- Include a critical assessment, counter-evidence, trade-offs, and explicit unknowns, not just a descriptive inventory.
- Produce a DOCX report that is detailed enough to function as a standalone product and technical briefing.

### 3. Exhaustive
Use when explicitly requested or when the decision has high stakes and broad coverage is necessary.

- Expand research across product, market, business, technology, operations, competition, and strategy.
- Investigate conflicting evidence and alternative explanations.
- Include a detailed evidence and limitations section.
- Do not confuse exhaustive with indiscriminate. Exclude low-value material.

## Scope and initial clarification

Identify the following from the user's request where possible:

- Product or company to analyse.
- Teardown, reconstruction, or both.
- Relevant geography and customer segment.
- Time period or as-of date.
- Desired depth.
- Intended audience or decision the analysis should support.

Ask a concise question only if an essential dimension is missing and cannot reasonably be inferred. Otherwise state sensible assumptions in the report and proceed.

For a teardown and reconstruction request, complete the teardown first. Base the reconstruction on findings, but label all proposed design decisions as proposals rather than facts about the existing product.

## Evidence discipline

The central rule is to distinguish what is known from what is inferred.

Use these labels consistently in the report:

- **Verified:** Directly supported by a credible source or direct product observation.
- **Inferred:** A reasoned conclusion based on observable evidence, technical principles, or multiple supporting facts. Explain the reasoning and confidence.
- **Unknown:** Not publicly discoverable or not reliably established.
- **Proposed:** A recommendation or design decision for a reconstructed product. It is not a claim about the existing product.

Do not present an inference as a verified fact. Do not turn an absence of public information into a confident claim.

### Source hierarchy

Prefer sources in roughly this order, depending on the claim:

1. Primary product surfaces: official website, app, product documentation, pricing pages, help centre, terms, API docs, product changelogs.
2. Regulatory filings, audited reports, investor presentations, official company announcements, and government or regulator publications.
3. Official engineering blogs, technical documentation, conference talks, patents, and published architecture material.
4. Research papers, reputable industry research, and established market-data providers.
5. Credible journalism and specialist publications.
6. User reviews, forums, app-store feedback, community discussions, and social posts for qualitative user experience signals.

Use user-generated content to understand reported experiences and recurring pain points, not as proof of company-wide performance or internal facts.

### Verification requirements

- Verify central claims against the original source wherever possible.
- For quantitative claims, inspect the underlying report, filing, dataset, paper, or original company statement. Do not rely solely on a secondary article repeating a number.
- Preserve the exact metric definition, unit, geography, period, population, sample size, and denominator.
- Distinguish revenue from GMV, bookings, gross merchandise sales, billings, payment volume, and other commonly confused measures.
- Distinguish users, active users, customers, subscribers, buyers, sellers, merchants, transactions, and accounts.
- Do not combine metrics from different periods or definitions as if directly comparable.
- Check whether figures are actuals, forecasts, estimates, targets, survey responses, or management guidance.
- Verify the publication date and whether a source has been updated, superseded, corrected, or retracted.
- When sources disagree, explain the discrepancy and identify which source is more authoritative. Do not silently choose the more convenient number.
- If a primary source is inaccessible, say so and lower the confidence of the claim.
- Do not invent internal metrics, CAC, LTV, retention, margins, conversion rates, model performance, architecture, database design, or operational processes.
- Use clearly labelled illustrative calculations only when useful. State every assumption and never present illustrative outputs as actual company data.
- Cite factual claims in the DOCX using numbered references or a consistent author-date system. Place a complete references section at the end. Include source links and access dates where appropriate.
- Keep citations close enough to the claims or tables they support. A references section alone is not sufficient if the reader cannot tell which source supports which claim.
- For tables, cite source-backed rows or add a source column. For charts, cite the underlying data.

### Evidence and confidence in analysis

For important findings, explain:

- What is directly observed or documented.
- What is inferred from that evidence.
- Why the inference is plausible.
- What alternative explanation may exist.
- Confidence: high, medium, or low.

Use confidence sparingly and consistently. Confidence is not a substitute for evidence.

## Research workflow

Use a deliberate multi-pass workflow. Adapt the amount of work to the selected mode.

### Pass 1: Frame the product

- Define the product, company, category, geography, and target audience.
- Identify the core user problem and the product's apparent value proposition.
- Determine the product's lifecycle stage where evidence supports it.
- Clarify whether the subject is a standalone product, a platform, a feature, or a multi-product ecosystem.
- Set the as-of date and relevant time period.

### Pass 2: Discover evidence

Gather evidence across:

- Official product pages and product surfaces.
- Pricing, plans, packaging, and monetisation pages.
- Help centre, onboarding, support, and policy documentation.
- App-store listings and credible user feedback.
- Company filings, investor materials, and official announcements.
- Engineering documentation, technical blogs, APIs, and public repositories.
- Competitor product pages and market information.
- Credible research and independent reporting.

Do not stop after reading the company's marketing pages. Marketing material is useful for positioning, not sufficient for a full teardown.

### Pass 3: Map the product

Map:

- Stakeholders and ecosystem participants.
- User segments, personas, and jobs-to-be-done.
- Core capabilities and supporting capabilities.
- User journeys and workflows.
- Key moments of value, friction, failure, and trust.
- Dependencies between features, users, data, and operations.

### Pass 4: Analyse the business

Investigate:

- Business model and value capture.
- Pricing, packaging, monetisation, and revenue streams.
- Cost structure and economic drivers.
- Acquisition and distribution.
- Retention, expansion, and engagement loops.
- Network effects and marketplace liquidity where relevant.
- Partnerships, supply-side dependencies, and operational constraints.
- Competitive position and defensibility.

Do not fabricate unit economics. If inputs are unavailable, show the economic model and identify the missing inputs rather than pretending to know the answer.

### Pass 5: Analyse the technology

Separate documented technology from architectural inference.

Investigate:

- Product surfaces and clients.
- Backend capabilities and service boundaries where known.
- Data entities and flows.
- APIs and integrations.
- Infrastructure and deployment information where documented.
- Security, privacy, reliability, and compliance implications.
- AI/ML components, model dependencies, evaluation, latency, and inference economics where relevant.

If the internal architecture is not public, produce a clearly labelled **plausible reference architecture**, not a factual diagram of the company's actual systems.

### Pass 5A: Perform a real technical teardown

A technical teardown is a core part of a comprehensive product analysis, not an optional paragraph at the end. Do not stop at naming a few technologies or drawing a generic box-and-arrow diagram. Explain how the product's important user-visible capabilities could be implemented and operated, using public evidence wherever available.

First establish the evidence boundary:

- **Documented implementation:** Explicitly described by official engineering publications, technical documentation, public repositories, patents, conference talks, job descriptions, or other credible sources.
- **Strongly supported inference:** Not explicitly disclosed, but strongly implied by observable product behaviour and well-established engineering requirements. Explain the reasoning.
- **Reference design:** A plausible implementation model created to explain the product. It is not a claim about the company's actual stack or architecture.
- **Unknown:** Internal implementation details that cannot be established responsibly.

Never turn a reference design into a factual architecture claim. Do not guess cloud vendors, programming languages, databases, message brokers, model providers, microservice boundaries, or deployment topology merely because they are common choices.

#### Technical investigation checklist

Investigate each area below when relevant. If an area is material but not publicly documented, explain what it likely needs to do, label the explanation as inference/reference design, and state what evidence would verify it.

1. **System context and product surfaces**
   - Web, mobile, desktop, API, partner, admin, and internal operations surfaces.
   - User roles and trust boundaries across those surfaces.
   - Major external dependencies: identity providers, payment processors, maps, messaging, data providers, model providers, app stores, and partner platforms.
   - Which capabilities are synchronous user-facing flows versus asynchronous background work.

2. **Domain decomposition and backend capabilities**
   - Identify the product's core domain concepts and bounded capabilities.
   - For each major capability, explain responsibility, inputs, outputs, state owned, dependencies, and failure behaviour.
   - Consider domains such as identity, profile, catalogue/listings, inventory, search, pricing, checkout, payments, order/reservation management, fulfilment, messaging, reviews, trust and safety, support, subscriptions, billing, analytics, and administration.
   - Distinguish logical capabilities from actual deployable services. Do not assume each capability is a microservice.
   - Explain critical workflows across capability boundaries and identify likely consistency requirements.

3. **Architecture views**
   Provide more than one useful view where the product complexity warrants it:
   - System context: users, product surfaces, external systems, and trust boundaries.
   - Container/component view: major applications, backend capabilities, data stores, queues, and integrations.
   - Critical request sequence: step-by-step flow for one or more high-value workflows.
   - Data-flow view: collection, validation, transformation, storage, retrieval, sharing, retention, and deletion.
   - Deployment/infrastructure view only where evidence supports it or clearly label it as a reference design.
   Every diagram must be product-specific, labelled, readable, and explained. Include evidence labels on inferred components.

4. **Data architecture and database design**
   - Identify core entities, identifiers, ownership, relationships, lifecycle states, and key invariants.
   - Explain likely transactional versus analytical data needs.
   - Consider relational, document, key-value, graph, search-index, object, time-series, and vector storage only where justified.
   - Explain indexing, partitioning/sharding, replication, caching, retention, archival, backup, and deletion needs where material.
   - Identify source-of-truth systems and derived/read-optimised views.
   - Address data quality, deduplication, event time versus processing time, schema evolution, lineage, and access control.
   - Include an entity-relationship diagram or schema table for complex products. Label any reconstructed schema as illustrative, not actual.
   - Never claim to know the company's actual schema unless it is published.

5. **API and integration architecture**
   - Map important client-to-backend and service-to-service interactions.
   - Identify public APIs, partner APIs, webhooks, SDKs, and integration constraints when documented.
   - For inferred interfaces, describe purpose and likely contract without presenting invented endpoint names as actual.
   - Examine authentication, authorisation, validation, pagination, versioning, rate limits, idempotency, retries, timeouts, and error semantics.
   - Explain synchronous APIs versus asynchronous events and webhooks.
   - Include example API contracts only in a clearly marked reference-design subsection.

6. **Search, discovery, ranking, and recommendation systems**
   Where discovery or matching is important, investigate the complete pipeline:
   - Query understanding, parsing, intent, constraints, and context.
   - Candidate retrieval and eligibility filtering.
   - Ranking and re-ranking signals.
   - Personalisation and user/item representations.
   - Availability, freshness, inventory, and business-rule constraints.
   - Diversity, exploration, cold start, and feedback loops.
   - Online serving, feature freshness, latency budgets, caching, and fallbacks.
   - Offline metrics and online experimentation, including guardrails and possible metric gaming.
   - Feedback data, position bias, popularity bias, and marketplace fairness where relevant.
   Explain which stages are documented and which are inferred. Do not describe a single public ML paper as the entire production ranking system.

7. **AI and machine learning systems**
   For each AI/ML capability, identify:
   - User or business task and why ML is appropriate.
   - Inputs, labels or feedback signals, features, and data rights.
   - Model family or approach, but only when supported or explicitly proposed.
   - Training, fine-tuning, evaluation, deployment, and inference lifecycle.
   - Batch versus real-time inference and online/offline feature consistency.
   - Evaluation dataset, baselines, metrics, segmentation, and known limitations.
   - Human review, override, escalation, and fallback behaviour.
   - Drift, monitoring, retraining triggers, reproducibility, and model governance.
   - Latency, compute, inference cost, and quality trade-offs.
   For generative AI systems, additionally examine retrieval, chunking, embeddings, vector/hybrid search, reranking, context construction, prompt and tool orchestration, permissions, grounding, citations, prompt injection, output validation, and agent/tool execution controls. Distinguish a demonstrated production capability from a marketing claim or a plausible design.

8. **Infrastructure, deployment, and scalability**
   Investigate what is known about:
   - Hosting and cloud footprint.
   - Compute and storage patterns.
   - CDN, edge delivery, caching, and static assets.
   - Load balancing, autoscaling, capacity planning, and regional deployment.
   - Containers, orchestration, CI/CD, infrastructure as code, and release strategy.
   - Background jobs, queues, streams, schedulers, and event-driven processing.
   - Multi-region design, disaster recovery, backup, and business continuity.
   - Cost allocation, utilisation, and infrastructure efficiency.
   If these details are not public, describe the product's scale requirements and a plausible architecture without attributing it to the company.

9. **Reliability and distributed-systems behaviour**
   Analyse failure modes in the product's most critical workflows:
   - Duplicate submissions, retries, idempotency, and exactly-once misconceptions.
   - Race conditions, concurrent updates, inventory/availability contention, and locking or reservation strategies.
   - Transaction boundaries, eventual consistency, sagas, compensation, and reconciliation.
   - Payment authorisation versus capture, refunds, chargebacks, and ledger correctness where relevant.
   - Queue backlogs, poison messages, dead-letter handling, and replay.
   - Dependency outages, graceful degradation, circuit breakers, timeouts, and fallback paths.
   - Data loss, stale reads, cache invalidation, and recovery.
   - Service-level indicators/objectives, error budgets, incident response, and postmortems where documented.
   Explain the user-visible consequence of each material failure mode. Do not invent internal SLOs or incident rates.

10. **Security, privacy, fraud, and abuse**
    - Authentication, session management, authorisation, role boundaries, and privileged access.
    - Encryption in transit and at rest, secrets management, key management, and audit logging.
    - Personal data categories, consent, purpose limitation, retention, deletion, and data portability.
    - Payment security and sensitive financial data boundaries where relevant.
    - Fraud, account takeover, spam, scraping, fake listings, chargebacks, collusion, and abuse patterns as relevant.
    - Content safety, moderation, reporting, appeals, and human escalation.
    - Threat surfaces from APIs, integrations, user-generated content, and AI tools.
    - Applicable regulatory or certification obligations, distinguishing legal requirements from voluntary controls.
    Do not claim compliance or certification without direct evidence. This is product analysis, not a security audit or legal opinion.

11. **Observability, experimentation, and internal tooling**
    - Product analytics events and instrumentation quality.
    - Logs, metrics, traces, dashboards, alerting, and incident diagnostics.
    - Feature flags, staged rollouts, experimentation platform, assignment, exposure logging, and guardrails.
    - Internal admin tools, operations consoles, support tooling, and audit trails.
    - Data pipelines, warehouse/lakehouse, semantic layers, and reporting where evidenced.
    - How teams could detect regressions in quality, conversion, latency, fraud, and cost.

12. **Technical economics and engineering trade-offs**
    Explain the cost and complexity implications of architecture choices:
    - Infrastructure and data costs.
    - Search/indexing and storage costs.
    - Payment and third-party provider fees.
    - AI inference, embedding, evaluation, and human review costs.
    - Reliability and support costs created by poor quality.
    - Build-versus-buy and vendor dependency.
    - Latency versus model complexity; consistency versus availability; flexibility versus operational burden.
    Do not fabricate actual cost figures. Use formulas or scenario analysis only when assumptions are explicit.

#### Technical evidence research strategy

Search specifically for engineering evidence rather than relying on product marketing pages. Look for official engineering blogs, architecture talks, conference presentations, API documentation, developer docs, public repositories, technical job descriptions, patents, security documentation, incident reports, and relevant research papers. Search for named technical systems and specific workflows. Use third-party technical analysis only as supporting evidence and label its limitations.

For each important technical claim, record:

- Component or capability.
- What is known.
- Evidence source and date.
- Evidence class: documented, inferred, reference design, or unknown.
- Confidence and rationale.
- What remains unverified.

If public technical disclosure is sparse, do not let the technology section collapse into a disclaimer. Build a useful reference architecture grounded in the actual product workflows, explicitly label it as such, and explain the engineering problems the product must solve.

### Pass 5B: Trace critical workflows end to end

Select at least two or three workflows that represent the product's core value or highest operational risk. For each, trace:

1. User action and client-side validation.
2. API request and identity/permission checks.
3. Backend capability or domain logic.
4. Data reads and writes.
5. External service calls or asynchronous events.
6. State transitions and business invariants.
7. User response and notifications.
8. Failure cases, retries, compensation, and support recovery.
9. Analytics events and success metrics.

For a marketplace, examples include listing publication, search-to-booking, payment and payout, cancellation/refund, and dispute resolution. For SaaS, examples include onboarding, core workflow execution, collaboration, billing, and permission changes. For AI products, trace prompt submission, retrieval, model/tool execution, validation, human escalation, and feedback capture.

Do not merely list steps. Explain how the steps fit together, where consistency matters, and what breaks if a dependency fails.

### Pass 6: Challenge the analysis

Actively look for evidence that could weaken the initial interpretation.

- Search for negative reviews, churn complaints, product limitations, outages, failed launches, and regulatory issues.
- Look for competitors that solve the problem differently.
- Test whether the claimed differentiator is actually differentiated.
- Check whether growth may be driven by paid acquisition, subsidies, bundling, regulation, or temporary market conditions rather than durable product value.
- Examine whether network effects are real, local, weak, or merely asserted.
- Consider disintermediation, commoditisation, platform dependency, and switching costs.
- Identify where the product's incentives may conflict with user interests.
- Separate correlation from causation.

### Pass 6A: Analyse user sentiment, friction, and drop-off

A serious teardown must investigate not only what the product offers, but what users value, dislike, fail to understand, abandon, work around, or leave. Treat this as a distinct evidence stream. Do not infer user sentiment from company marketing or a handful of anecdotes.

#### User voice research

Collect qualitative evidence from relevant sources, prioritising first-hand user reports:

- App Store and Google Play reviews, including review dates, ratings, versions, and developer responses.
- Product-specific communities, forums, Reddit discussions, public support threads, and user groups.
- Public customer interviews, case studies, testimonials, and independent product reviews.
- Public feature requests, issue trackers, community roadmaps, and changelog discussions.
- Public complaints about billing, cancellation, onboarding, reliability, support, accessibility, privacy, and product quality.
- Positive accounts explaining why users choose, recommend, repeatedly use, or pay for the product.

Code the feedback into themes rather than copying isolated comments. For each theme capture:

- User segment and context, if identifiable.
- User goal or job being attempted.
- Positive outcome or pain point.
- Journey stage and feature involved.
- Severity and consequence.
- Frequency within the collected sample, not the entire user base.
- Recency and whether the issue appears resolved or persists.
- Supporting examples and source links.
- Confidence and representativeness limitations.

Separate **what users love** from **what the company says is valuable**. Identify recurring value drivers such as convenience, speed, trust, price, selection, quality, reliability, status, control, integrations, or outcomes. Identify recurring dissatisfaction such as friction, confusing UX, hidden costs, poor quality, lack of control, unreliable service, weak support, missing features, performance, privacy concerns, or unmet expectations.

Do not call a theme widespread based only on a small or self-selected sample. State the number and type of sources reviewed where feasible. Reviews are biased toward unusually positive or negative experiences and must not be treated as representative survey data.

#### Funnel and drop-off analysis

Map the product's most important user funnels and identify where users may abandon, stall, fail, or downgrade. Select funnels appropriate to the product, for example:

- Acquisition landing page → signup → verification → onboarding → activation.
- Search/discovery → product detail → comparison → checkout → payment → fulfilment/completion.
- Free usage → habit formation → paywall/upgrade → paid activation → renewal.
- Seller/provider onboarding → verification → first listing → first transaction → repeat supply.
- AI workflow: prompt/input → context upload → generation/tool execution → review/edit → export/share → repeat use.

For every stage, define the user intent, required action, likely friction, system dependency, desired next step, observable event, and possible abandonment reason. Show the funnel as a table or diagram. Distinguish:

- **Measured drop-off:** Supported by reliable product analytics or a published study with clear definitions.
- **Reported friction:** Users explicitly describe difficulty or abandonment.
- **Inferred drop-off risk:** A reasoned hypothesis based on journey design, constraints, or observed complaints.
- **Unknown:** Requires internal event data, usability testing, or cohort analysis.

Never invent conversion rates or claim to know the actual point of highest abandonment without data. If internal analytics are unavailable, produce a **funnel risk map**, not a fabricated funnel. For each hypothesised drop-off, specify the event instrumentation and analysis needed to validate it.

Where data exists, segment funnel performance by acquisition channel, geography, device, new versus returning users, user type, plan, cohort, and relevant product category. Check for selection bias, denominator changes, seasonality, and survivorship bias. Distinguish user abandonment from technical failure, eligibility rejection, supply unavailability, and deliberate choice.

#### Retention, churn, and reactivation

Investigate:

- Reasons users return and form habits.
- Reasons users stop using, cancel, downgrade, or switch.
- Time-to-value and time-to-first-success.
- Onboarding completion and early activation barriers.
- Repeat purchase or transaction cadence.
- Cohort retention and frequency, where data exists.
- Switching triggers and destination products.
- Win-back, reactivation, and cancellation flows.
- Whether churn is caused by product dissatisfaction, lack of need, price, competition, seasonality, life events, or one-time use cases.

Separate voluntary churn, involuntary churn (for example payment failure), inactivity, non-renewal, and natural completion of a one-off job. Do not treat every inactive user as churned. For marketplaces, analyse both demand-side and supply-side retention, including multi-homing and disintermediation.

#### User pain-point and unmet-needs register

Create a prioritised register with fields such as:

| Field | What to capture |
|---|---|
| User segment | Who experiences the issue |
| Job/context | What the user was trying to accomplish |
| Pain point | Specific friction or unmet need |
| Evidence | Sources, examples, and sample size |
| Journey stage | Where it occurs |
| Severity | Impact on task success, trust, money, or safety |
| Frequency signal | Observed sample frequency, not assumed population prevalence |
| Workaround | How users currently compensate |
| Product consequence | Abandonment, lower conversion, support burden, churn, or lost trust |
| Confidence | High, medium, or low |
| Validation needed | Analytics, interviews, usability tests, or operational data |

Rank pain points using user impact, evidence strength, affected segment importance, strategic relevance, and feasibility of validation. Do not equate the loudest complaint with the largest opportunity.

### Pass 6B: Identify product gaps and competitive opportunities

Move from describing weaknesses to explaining where a competitor or new entrant could create a better product. A gap is not automatically an opportunity: it must be important to a defined segment, inadequately served by existing alternatives, and feasible to address sustainably.

#### Gap taxonomy

Examine gaps across:

1. **Experience gaps:** Confusing flows, excessive steps, poor accessibility, weak information hierarchy, inconsistent interactions, or lack of user control.
2. **Functional gaps:** Missing capabilities, incomplete workflows, poor integrations, limited customisation, or weak edge-case handling.
3. **Performance gaps:** Slow response, poor reliability, downtime, latency, battery/data usage, or weak offline behaviour.
4. **Trust and safety gaps:** Fraud, privacy concerns, poor moderation, unclear policies, weak dispute resolution, or insufficient transparency.
5. **Economic gaps:** Poor price/value, hidden fees, unpredictable costs, weak seller/provider economics, or expensive cost-to-serve.
6. **Service and operations gaps:** Slow support, poor fulfilment, weak onboarding, inconsistent quality, or inadequate recovery.
7. **Technical gaps:** Data silos, poor APIs, weak extensibility, scaling constraints, brittle integrations, security weaknesses, or model limitations where evidenced.
8. **Segment gaps:** Underserved geographies, accessibility needs, small businesses, enterprise users, power users, newcomers, or specialist workflows.
9. **Strategic gaps:** Overdependence on one channel, weak ecosystem, limited differentiation, poor interoperability, or vulnerability to platform changes.

For every material gap, state the evidence, affected segment, existing workaround, competitor response, user/business consequence, confidence, and what would disprove the hypothesis.

#### Competitive benchmarking

Compare the subject with direct competitors, indirect alternatives, substitutes, and best-in-class products from adjacent categories where useful. Compare actual workflows, not just feature checklists. Benchmark:

- Time and steps to complete the core job.
- Onboarding and time-to-first-value.
- Search/discovery quality and relevance.
- Price transparency and total cost.
- Core feature depth and edge-case coverage.
- Reliability, performance, and support.
- Trust, privacy, safety, and user control.
- Integrations, APIs, portability, and extensibility.
- Personalisation and accessibility.
- Seller/provider/creator economics where relevant.
- Monetisation and pricing flexibility.

Use current product pages, hands-on product walkthroughs when available, documentation, pricing, release notes, and user evidence. Record the date and scope of each comparison. Do not mark a capability absent merely because it was not found in a quick search. Use **not verified** when evidence is incomplete.

Build a comparison matrix that identifies:

- Where the subject is stronger.
- Where competitors are stronger.
- Where all major players are weak.
- Where a competitor's apparent advantage has trade-offs.
- Which segments are underserved.
- Which differences are meaningful to users versus cosmetic parity.

#### Opportunity and differentiation analysis

Translate validated gaps into opportunity hypotheses. For each opportunity, specify:

- Target segment and unmet job.
- Problem and evidence.
- Proposed improvement or differentiated capability.
- Why current solutions fail or under-serve the segment.
- User value and expected behavioural change.
- Business model and value-capture logic.
- Technical and operational requirements.
- Competitor response and ease of imitation.
- Risks, dependencies, and unintended consequences.
- Cheapest credible validation experiment.
- Success metric and guardrail.

Prioritise opportunities using a transparent framework. A practical score can combine user impact, evidence confidence, segment reach or strategic value, differentiation potential, business viability, and implementation effort/risk. Explain weights and assumptions. Do not present a subjective score as objective truth.

Separate opportunities into:

- **Parity fixes:** Necessary to meet baseline expectations.
- **Conversion improvements:** Remove friction from acquisition, activation, or purchase.
- **Retention improvements:** Increase recurring value and reasons to return.
- **Trust and quality improvements:** Reduce risk and improve successful outcomes.
- **Differentiation bets:** Create a defensible reason to choose the product.
- **Platform opportunities:** APIs, integrations, ecosystem, data, or infrastructure capabilities.
- **New-market or segment opportunities:** Serve a distinct underserved customer group.

For each top recommendation, explain how the product could be better in practice, not just which feature to copy. Include trade-offs and what the incumbent might do in response.

### Pass 6C: Convert findings into an actionable improvement plan

Create a prioritised improvement roadmap tied directly to evidence. Organise recommendations by horizon, for example:

- **Immediate:** Remove severe friction, fix confusing or broken workflows, improve transparency, instrument missing events, and address high-confidence trust/reliability issues.
- **Near term:** Improve activation, funnel conversion, core workflow completion, retention, support recovery, and critical integrations.
- **Longer term:** Build differentiated capabilities, technical platform advantages, new business models, ecosystem effects, or new segment offerings.

For each recommendation include problem, target segment, evidence, proposed change, expected mechanism of impact, product/technical dependencies, effort or complexity, risk, success metric, guardrail, and validation plan. Identify quick wins separately from strategic bets. Do not promise uplift percentages without evidence or a transparent model.

Tie each recommendation to a measurable hypothesis, for example: “If we simplify identity verification for eligible low-risk users, then onboarding completion should improve without increasing fraud loss.” Specify the experiment or analysis needed to test it.

### Pass 7: Close material gaps

Return to research when a key conclusion depends on missing or conflicting evidence. Prioritise gaps that could materially change the conclusion. Do not spend time filling trivia.

### Pass 8: Synthesise

Convert evidence into a coherent explanation of:

- How the product works for users.
- Why the product is structured as it is.
- How the business captures value.
- What capabilities and systems enable it.
- What appears defensible or vulnerable.
- What remains unknown.
- What the evidence implies for product and business decisions.

### Pass 9: Reconstruct if requested

Use the teardown as the evidence base for a proposed product blueprint. Label the entire reconstruction section as **Proposed design**. Make assumptions explicit and identify decisions requiring validation.

### Pass 10: Quality audit

Before delivering, check factual accuracy, analytical completeness, internal consistency, source quality, table and chart integrity, and DOCX rendering. The report must be useful as a standalone document.

## Product analysis framework

Do not mechanically fill every subsection. Select and adapt the relevant dimensions to the product category.

### 1. Product overview and positioning

Analyse:

- Product purpose and category.
- Core value proposition.
- Target users and buyers.
- Primary use cases.
- Positioning and differentiation.
- Product maturity and lifecycle stage, if supported.
- Product portfolio and ecosystem relationships.

Distinguish the company's stated positioning from the value users appear to receive.

### 2. Problem and alternatives

Explain:

- The user problem or job-to-be-done.
- How users solve it today.
- Existing substitutes and workarounds.
- Frequency, urgency, and importance of the problem.
- Switching barriers and adoption friction.
- Whether the product solves a painful problem or creates a new behaviour.

### 3. Stakeholder ecosystem

Identify relevant parties, such as:

- End users.
- Buyers and budget owners.
- Suppliers, creators, merchants, or service providers.
- Developers and integration partners.
- Advertisers.
- Payment providers.
- Regulators and other institutions.
- Internal operators and support teams.

Explain incentives, dependencies, value exchanged, and potential conflicts.

### 4. User personas and jobs-to-be-done

Develop evidence-grounded user segments. For each relevant segment, capture:

- Context and goals.
- Job-to-be-done.
- Current alternatives.
- Main pain points.
- Desired outcomes.
- Adoption triggers.
- Barriers and objections.
- Product value received.

Do not invent demographic detail. If personas are analytical hypotheses rather than research-backed profiles, label them as inferred.

### 5. Feature and capability decomposition

Create a structured inventory of important capabilities.

For each capability, where possible, include:

- Feature or capability.
- User problem addressed.
- Primary user or stakeholder.
- User value.
- Business value.
- Dependencies.
- Monetisation relationship.
- Evidence status.
- Limitations or friction.

Distinguish user-facing features from underlying platform capabilities and operational capabilities.

Prioritise capabilities by strategic importance, not by how visible or novel they appear.

### 6. User journeys and workflows

Map the important end-to-end journeys, such as:

- Discovery and acquisition.
- Signup and onboarding.
- Activation and first value.
- Core task completion.
- Repeat usage and retention.
- Payment or purchase.
- Collaboration or sharing.
- Support, recovery, cancellation, and offboarding.

For each journey, identify:

- Trigger.
- User intent.
- Steps and decisions.
- Product touchpoints.
- Data or system dependencies.
- Friction and failure points.
- Success outcome.
- Relevant metrics.

Use flow diagrams where they clarify branching, dependencies, or handoffs.

### 7. Product and system architecture

Analyse documented architecture where available. Otherwise construct a clearly labelled reference architecture.

Potential layers:

- Client applications and interfaces.
- Identity and access.
- Application services.
- Domain services.
- APIs and integrations.
- Data storage and processing.
- Search, recommendations, and personalisation.
- Analytics and experimentation.
- Payments and billing.
- Notifications and communications.
- Security, observability, and reliability.

Explain how major capabilities interact. Do not use generic architecture diagrams that could describe any software product without product-specific reasoning.

### 8. Business model and monetisation

Identify:

- Who pays.
- What they pay for.
- Pricing metric and packaging.
- Revenue streams.
- Free-to-paid conversion logic.
- Transaction or subscription mechanics.
- Advertising, licensing, usage-based, marketplace, or hybrid models.
- Incentives and value exchange between stakeholders.
- Monetisation constraints and risks.

Separate confirmed pricing and revenue information from inferred monetisation logic.

### 9. Product economics and unit economics

Where data exists, analyse relevant economics:

- Revenue per customer, user, seat, transaction, or order.
- Gross margin and contribution margin.
- Customer acquisition cost.
- Lifetime value.
- Payback period.
- Retention and churn.
- Take rate and transaction economics.
- Cost to serve.
- Infrastructure or AI inference cost.
- Subsidies and incentives.
- Working capital and fulfilment costs.

Use only comparable, correctly defined data. If inputs are unavailable, provide formulas, explain the drivers, and state what data is needed. Do not manufacture estimates.

### 10. Growth and distribution

Analyse:

- Acquisition channels.
- Organic and paid distribution.
- Partnerships and integrations.
- Referral and sharing loops.
- SEO, content, community, and developer distribution.
- Sales-led, product-led, or hybrid motion.
- Activation and onboarding.
- Retention and expansion.
- Network effects and viral loops, where relevant.

Distinguish observed growth mechanisms from speculative explanations.

### 11. Competitive landscape

Compare meaningful alternatives, not just companies in the same broad category.

For each competitor or substitute, compare relevant dimensions such as:

- Target segment.
- Core use case.
- Value proposition.
- Product capabilities.
- Pricing and packaging.
- Distribution.
- Business model.
- Differentiation.
- Strengths and weaknesses.

Explain the basis and date of comparison. Do not claim a feature is unique without checking relevant alternatives.

### 12. Operating model

Investigate operational work required to deliver the product:

- Customer support and success.
- Trust and safety.
- Content moderation.
- Merchant, supplier, or creator operations.
- Fulfilment and logistics.
- Fraud and risk management.
- Compliance and legal processes.
- Data quality and review.
- Human-in-the-loop processes.
- Service reliability and incident response.

For products with offline components, analyse the interaction between software and physical operations.

### 13. Product metrics and measurement

Choose metrics based on the product's value creation mechanism. Do not blindly apply generic SaaS metrics to every product.

Potential metric categories:

- Acquisition.
- Activation.
- Engagement.
- Retention.
- Monetisation.
- Customer experience.
- Reliability and quality.
- Marketplace liquidity.
- Supply quality.
- Trust and safety.
- AI quality, latency, cost, and human escalation.

For important metrics, define:

- Metric name.
- Exact formula.
- Numerator and denominator.
- Cohort or population.
- Time window.
- Segmentation.
- Data source required.
- Interpretation and limitations.

Distinguish leading indicators from lagging outcomes. Avoid vanity metrics without a clear decision use.

### 14. Strategic assessment

Assess:

- Strength of the problem-solution fit.
- Product differentiation.
- User value and experience quality.
- Distribution advantages.
- Business model resilience.
- Economic sustainability.
- Operational complexity.
- Technical differentiation.
- Switching costs and defensibility.
- Platform, regulatory, and ecosystem dependencies.
- Key risks and strategic opportunities.

Make a clear argument. Do not end with a generic list of strengths and weaknesses. Explain which factors matter most and why.

## Category-specific analysis lenses

Apply only the lenses relevant to the product.

### Marketplaces

Investigate:

- Supply and demand sides.
- Liquidity and matching efficiency.
- Geographic or category density.
- Time to match and fulfilment.
- Take rate and transaction value.
- Supply quality and reliability.
- Disintermediation.
- Subsidies and incentive dependence.
- Multi-homing and switching.
- Trust, safety, fraud, and dispute resolution.
- Local network effects and cold-start strategy.

### SaaS and enterprise software

Investigate:

- Buyer, user, administrator, and procurement stakeholders.
- Time-to-value and activation.
- Workflow depth and integration.
- Seat expansion and usage expansion.
- Renewal, churn, and net revenue retention where data exists.
- Pricing metric and packaging.
- Implementation and support burden.
- Security, compliance, and enterprise readiness.
- Switching costs and system-of-record position.

### Social and creator products

Investigate:

- Content supply and demand.
- Creator incentives and monetisation.
- Feed and recommendation mechanisms where known.
- Engagement and retention loops.
- Network effects and cold start.
- Moderation, safety, spam, and abuse.
- Advertiser or subscription economics.
- Content rights and platform dependency.

### E-commerce and commerce platforms

Investigate:

- Assortment and supply.
- Search, discovery, and merchandising.
- Conversion and checkout.
- Payments and fraud.
- Fulfilment, delivery, and returns.
- Inventory and working capital.
- Repeat purchase and loyalty.
- Gross margin and contribution margin.
- Marketplace versus first-party economics.

### Fintech and financial products

Investigate:

- Customer trust and adoption.
- Payments, lending, savings, investing, or insurance workflows.
- Revenue and fee model.
- Credit, fraud, market, and operational risk.
- Compliance and regulatory obligations.
- Capital, liquidity, and balance-sheet dependencies where relevant.
- Loss rates, approval rates, and unit economics where data exists.
- Banking, payment, and infrastructure partners.

Do not provide legal or financial advice. Describe product and business implications and flag where specialist review is needed.

### AI products

Investigate:

- User workflow and task suitability.
- Model and provider dependencies.
- Proprietary data access and data rights.
- Retrieval, context, memory, tools, and orchestration.
- Evaluation methodology and benchmark relevance.
- Accuracy, reliability, and failure modes.
- Latency and inference cost.
- Human review and escalation.
- Privacy, security, and safety.
- Model switching and commoditisation risk.
- Defensibility beyond access to a foundation model.

Distinguish demonstrated capabilities from marketing claims. Do not infer that a product uses a particular model or architecture without evidence.

### Developer tools and platforms

Investigate:

- Developer persona and workflow.
- Time-to-first-success.
- Documentation and developer experience.
- APIs, SDKs, integrations, and extensibility.
- Reliability and performance.
- Ecosystem and community.
- Open-source versus commercial boundaries.
- Usage-based pricing and cost drivers.
- Platform lock-in and migration costs.

## Structured presentation requirements

A strong report must not be a wall of paragraphs. Use prose for reasoning and structured visual formats for information that is easier to compare, scan, or understand spatially.

### Tables

Use tables as a first-class presentation format when they improve clarity. Consider:

- Executive summary dashboard.
- Product and market overview.
- Stakeholder ecosystem matrix.
- Persona and JTBD matrix.
- Feature and capability inventory.
- User journey map.
- Competitor comparison.
- Business model and revenue stream table.
- Unit economics definitions and calculations.
- Growth loop analysis.
- Product metrics dictionary.
- Architecture component inventory.
- Technology trade-off comparison.
- Risk register.
- Evidence and unknowns register.
- Reconstruction requirements and prioritisation matrix.
- Roadmap and milestone table.

Tables must be readable and decision-useful. Avoid excessively wide tables. Split a large table into smaller logical tables rather than shrinking text until it is unreadable.

### Charts

Use charts when actual quantitative data reveals a pattern, comparison, distribution, trend, or relationship that prose cannot show as clearly.

Suitable charts include:

- Revenue or usage trends.
- Segment mix.
- Cohort retention.
- Funnel conversion.
- Market share estimates.
- Unit economics sensitivity.
- Cost composition.
- Competitor positioning when dimensions are defensible.

Every chart must state its title, units, period, population or scope, and source. Clearly distinguish reported data from calculated values and illustrative scenarios. Never create a chart from invented values merely to make the report look visual.

If quantitative data is unavailable, do not force a chart. Use a framework, table, or diagram instead.

### Diagrams

Use diagrams when relationships, flows, or system boundaries matter.

Suitable diagrams include:

- User journey and workflow.
- Stakeholder ecosystem.
- Marketplace value exchange.
- Growth loops.
- Product capability map.
- System context and component architecture.
- Data flow.
- AI request and evaluation flow.
- Proposed product architecture.
- Roadmap or decision flow.

Diagrams must be specific to the product and explained in accompanying text. Label inferred or proposed architecture clearly. Avoid decorative diagrams that add no analytical value.

### Composition rule

For each major section, choose the format that best communicates the analysis:

- Paragraphs for explanation, interpretation, and argument.
- Tables for comparison, inventories, structured evidence, and decisions.
- Charts for real quantitative patterns.
- Diagrams for journeys, systems, flows, and relationships.
- Bullets for concise lists of findings, risks, and actions.

Use a mix of formats throughout the DOCX. Do not turn every paragraph into a table, and do not create tables where a short paragraph is clearer.

## Reconstruction framework

Use this section only when the user requests reconstruction, asks how to build a similar product, or clearly wants an actionable product blueprint.

The reconstruction is a proposal, not a claim about the existing product. State assumptions, open decisions, and validation needs.

### 1. Product thesis and opportunity

Define:

- Problem worth solving.
- Target segment.
- Why now.
- Current alternatives.
- Proposed value proposition.
- Differentiation hypothesis.
- Main assumptions requiring validation.

### 2. Target users and market

Define user segments, buyers, stakeholders, jobs-to-be-done, adoption triggers, and constraints. Avoid unsupported market-size claims.

### 3. MVP scope and non-goals

Specify:

- Core MVP outcome.
- Must-have capabilities.
- Deferred capabilities.
- Explicit non-goals.
- Dependencies.
- Release assumptions.
- Success criteria.

Keep the MVP narrow enough to test the core value proposition.

### 4. Product requirements document

For each requirement, include:

- Requirement ID.
- User or business problem.
- User story or use case.
- Functional requirement.
- Priority.
- Acceptance criteria.
- Dependencies.
- Edge cases.
- Evidence or rationale.

Acceptance criteria must be testable and unambiguous.

### 5. Prioritisation

Use a transparent method such as RICE, MoSCoW, or impact versus effort. Explain assumptions and scoring. Do not imply that a numerical score is objective when inputs are estimates.

### 6. User journeys and UX flows

Define key journeys, screens or states, user decisions, error handling, empty states, permissions, and recovery paths. Include diagrams where useful.

### 7. Technical architecture

Propose a coherent architecture based on requirements and expected scale.

Cover relevant areas:

- Client applications.
- Backend services.
- APIs and integrations.
- Authentication and authorisation.
- Data storage.
- Search and indexing.
- Event processing.
- Analytics.
- Notifications.
- Payments.
- Observability.
- Security and privacy.
- Deployment and operations.

Explain major design decisions and trade-offs. Avoid prescribing a complex microservice architecture without a clear need.

### 8. Data model and database design

Define key entities, relationships, identifiers, lifecycle, and important constraints. Include a schema or entity relationship diagram where useful.

Do not over-specify fields that are not required by the product requirements. Identify sensitive data and access controls.

### 9. API specifications

Where useful, define:

- Endpoint and method.
- Purpose.
- Authentication.
- Request schema.
- Response schema.
- Validation.
- Error responses.
- Rate limits and idempotency.
- Versioning considerations.

Use consistent naming and realistic examples. Mark proposed endpoints as proposed.

### 10. AI/ML architecture

Include only if the product requires AI/ML.

Cover:

- Task and model requirements.
- Model selection criteria.
- Data sources and permissions.
- Retrieval and grounding.
- Prompting and orchestration.
- Tool access and permissions.
- Evaluation datasets and metrics.
- Offline and online evaluation.
- Human review and escalation.
- Monitoring and drift.
- Latency and cost controls.
- Failure handling and fallback behaviour.

Do not add AI merely to make the product appear innovative.

### 11. Non-functional requirements

Specify relevant requirements for:

- Performance and latency.
- Availability and reliability.
- Scalability.
- Security.
- Privacy and data retention.
- Accessibility.
- Maintainability.
- Observability.
- Compliance.
- Disaster recovery.

Use measurable targets only when they are justified or clearly labelled as proposed targets.

### 12. Technology stack and trade-offs

Recommend technologies based on requirements, team capability, cost, ecosystem, and operational complexity.

For each major choice, explain:

- Why it fits.
- Alternatives considered.
- Trade-offs.
- Migration or lock-in implications.

Do not choose tools solely because they are popular.

### 13. Monetisation and economics

Propose pricing and revenue logic, cost drivers, and a unit economics model. Label all assumptions. Identify the data needed to validate willingness to pay and sustainable margins.

### 14. Roadmap and delivery plan

Break delivery into logical phases, such as:

- Discovery and validation.
- Prototype.
- MVP.
- Beta.
- Launch.
- Iteration and scale.

For each phase, include outcomes, dependencies, risks, and exit criteria. Avoid fake precision in timelines when team size and constraints are unknown.

### 15. Launch and growth strategy

Define target launch segment, positioning, acquisition channels, onboarding, activation, retention, feedback loops, and experiments.

### 16. KPIs and experiments

Create a metric tree or measurement framework. Define north-star metric, input metrics, guardrails, formulas, data sources, and review cadence.

Propose experiments with hypotheses, target segments, success metrics, guardrails, and decision rules.

### 17. Risks and open decisions

Include product, market, operational, technical, security, privacy, regulatory, and commercial risks as relevant. Assign likelihood and impact only when there is a defensible basis. List unresolved decisions and the evidence needed to make them.

## DOCX deliverable requirements

For substantial work, generate one cohesive DOCX file. The DOCX is the primary deliverable. Do not create multiple separate documents unless the user explicitly requests them.

### Required depth for a Comprehensive teardown

Comprehensive means an actual investigation and explanation, not a short executive overview padded with headings. Scale the report to the product's complexity and the evidence available. Do not chase an arbitrary page count, but do not compress a complex platform into a handful of pages.

For a substantial software product, the report should normally include:

- A concise executive synthesis and a product/market fact base.
- Stakeholder, user-segment, JTBD, capability, and journey analysis.
- At least one detailed end-to-end core journey and a second journey when the product has materially different user roles or workflows.
- A business model, monetisation, cost-driver, growth-loop, competitive, and operating-model analysis.
- A substantive technical section with a system context diagram, component/capability map, critical workflow sequence, data model or entity map, and relevant API, search/ML, infrastructure, reliability, security, and observability analysis.
- An explicit distinction between documented implementation and inferred/reference architecture.
- A product metrics tree or measurement framework with formulas and guardrails.
- Strategic conclusions, prioritised recommendations, risks, and a detailed unknowns/evidence-gap register.
- Source references close to factual claims and a complete reference list.

Depth should come from explaining mechanisms, dependencies, trade-offs, and implications. A table containing feature names is not feature analysis. A diagram containing generic boxes is not architecture analysis. A list of technologies is not a technical teardown. Each major section must answer: what is happening, how it works, why it matters, what evidence supports it, what can fail, and what the implications are.

For products with substantial engineering complexity, devote meaningful report space to technical analysis. If technical details are undisclosed, explicitly state that limitation and provide a product-specific reference architecture. Never fabricate internal details to make the report look comprehensive.

### Standard teardown report structure

Adapt sections to relevance. Do not include empty headings just to match the list.

1. Cover page and report metadata.
2. Executive summary.
3. Product and market overview.
4. Problem and value proposition.
5. Stakeholder ecosystem.
6. User personas and jobs-to-be-done.
7. Feature and capability analysis.
8. User journeys and workflows.
9. Product and technical architecture, including system context, backend capability map, critical workflow traces, data architecture, APIs/integrations, search/recommendations, AI/ML, infrastructure, reliability, security, and observability as relevant.
10. Business model and monetisation.
11. Product economics and unit economics.
12. Growth and distribution.
13. Competitive landscape.
14. Operating model.
15. Product metrics and measurement.
16. User sentiment, likes, dislikes, and recurring feedback themes.
17. Funnel analysis, drop-off risks, activation, retention, and churn.
18. Product gaps, unmet needs, and competitive benchmarking.
19. Prioritised opportunities and improvement roadmap.
20. Strategic assessment.
21. Unknowns, assumptions, evidence gaps, and limitations.
22. References.

### Reconstruction report structure

When reconstruction is requested, add a clearly separated second part to the same DOCX:

1. Proposed product thesis.
2. Target users and market.
3. Problem and value proposition.
4. MVP scope and non-goals.
5. Product requirements.
6. User stories and acceptance criteria.
7. Feature prioritisation.
8. User journeys and UX flows.
9. Technical architecture.
10. Data model and database design.
11. API specifications.
12. AI/ML architecture, if relevant.
13. Security and non-functional requirements.
14. Technology stack and trade-offs.
15. Monetisation and economics.
16. Roadmap and milestones.
17. Launch and growth strategy.
18. KPIs and experiments.
19. Risks and open decisions.

### DOCX design and readability

- Use a clean, professional report layout.
- Include a title, product name, report date, scope, and as-of date.
- Use consistent heading hierarchy and styles.
- Include an automatically maintainable table of contents when practical.
- Use page numbers and useful headers or footers.
- Use readable typography, spacing, and margins.
- Use tables with clear header rows, appropriate widths, and repeated header rows across pages where supported.
- Prevent important table rows from splitting across pages where practical.
- Avoid excessive page breaks, large blank areas, orphaned headings, and stranded lines.
- Keep charts legible and label axes, units, dates, and sources.
- Keep diagrams legible and ensure labels are not clipped.
- Use captions and source notes for tables, charts, and diagrams.
- Make references usable, with working hyperlinks where possible.
- Do not use decorative images that add no analytical value.
- Do not let visual polish conceal weak evidence or thin analysis.

### DOCX quality control

After generating the document:

1. Reopen or inspect the generated DOCX using available tools.
2. Check that all intended sections and tables are present.
3. Check that references and hyperlinks are preserved.
4. Render to PDF or images if the environment supports it, then inspect pages.
5. Check for broken tables, split rows, clipped diagrams, unreadable charts, blank pages, inconsistent headings, awkward page breaks, and orphaned text.
6. Fix layout defects and regenerate if necessary.
7. If visual rendering is unavailable, perform the strongest structural inspection available and disclose that limitation.

Do not claim the DOCX was visually inspected if it was not.

## Chat response after document creation

Keep the chat response concise. Include:

- A short description of what the report covers.
- The main conclusion or most important finding, if supported.
- A link to the generated DOCX using the exact path returned by the file-generation environment.
- Important limitations, if any.

Do not paste the full report into chat unless requested.

## Quality rubric

Before delivery, assess the work against these dimensions:

| Dimension | Quality standard |
|---|---|
| Product understanding | Explains the product's real user problem, value, workflows, and capabilities |
| Business analysis | Explains value capture, growth, economics, incentives, and operating constraints |
| Technical analysis | Explains product-specific system components, data, APIs, critical workflows, failure behaviour, architecture trade-offs, and relevant ML/infrastructure/security; separates documented facts from inference |
| Evidence quality | Uses credible sources, verifies central claims, and preserves definitions and context |
| User insight | Distinguishes what users value, dislike, abandon, and request using appropriately qualified evidence |
| Funnel and retention analysis | Maps conversion stages, identifies measured versus hypothesised drop-off, and explains activation, churn, and reactivation |
| Gap and competitive analysis | Identifies evidenced underserved needs and explains how a product could compete through meaningful differentiation |
| Actionability | Prioritises improvements with hypotheses, validation plans, metrics, guardrails, and technical/operational dependencies |
| Critical thinking | Tests assumptions, includes counter-evidence, and identifies failure modes |
| Category adaptation | Uses the correct analytical lens for the product category |
| Structured communication | Uses appropriate prose, tables, charts, and diagrams |
| Actionability | Produces clear implications, opportunities, and recommendations |
| DOCX quality | Delivers a readable, complete, correctly rendered standalone document |

A report is not complete merely because every heading has content. Prioritise explanatory power, evidence, and decision usefulness. A short prompt must still result in the full Comprehensive scope. Do not compress away the technical teardown, user sentiment, funnel risk map, competitive comparison, or opportunity analysis merely because the user did not name those dimensions. Page count is not a quality target; sufficient depth to explain mechanisms, evidence, trade-offs, and implications is.

## Failure modes to avoid

- Repeating marketing claims as independent analysis.
- Listing features without explaining user value or strategic purpose.
- Treating every product as SaaS.
- Applying generic metrics without understanding the product's value mechanism.
- Claiming to know proprietary architecture or internal algorithms.
- Inventing financial or operating metrics.
- Confusing revenue, GMV, bookings, payment volume, and other financial measures.
- Treating a handful of reviews as representative of all users.
- Claiming actual funnel drop-off or churn reasons without product analytics or credible cohort evidence.
- Ignoring positive user feedback and analysing only complaints.
- Treating feature requests as validated demand without understanding the underlying job or willingness to use/pay.
- Listing product gaps without identifying the affected segment, evidence, consequence, or existing workaround.
- Recommending that a competitor simply copy features without a defensible differentiation thesis.
- Ranking opportunities using opaque scores or unsupported impact estimates.
- Calling a product's feature unique without competitor verification.
- Describing network effects without explaining the mechanism and evidence.
- Producing a generic architecture diagram unrelated to the product.
- Treating a one-paragraph architecture sketch as a complete technical teardown.
- Listing fashionable technologies without explaining why the product needs them or whether their use is verified.
- Omitting data models, API interactions, workflow sequences, failure handling, or security considerations from a complex software teardown.
- Treating one published engineering article or ML paper as a complete description of a company's production system.
- Adding AI/ML to a reconstruction without a genuine use case.
- Producing long prose where a table or diagram would be clearer.
- Creating decorative tables, charts, or diagrams with no analytical purpose.
- Creating a polished DOCX with weak research.
- Generating a DOCX but failing to inspect its structure and rendering.
- Presenting proposed reconstruction decisions as facts about the existing product.
- Filling gaps with confident speculation instead of marking them unknown.

## Final delivery checklist

Before finalising, verify:

- [ ] The analysis answers the user's actual question and respects scope.
- [ ] The selected depth is appropriate.
- [ ] Product category-specific lenses are applied where relevant.
- [ ] Important claims are supported by credible evidence.
- [ ] Central quantitative claims are checked against original sources where possible.
- [ ] Definitions, dates, populations, units, and denominators are preserved.
- [ ] Verified facts, inferences, unknowns, and proposals are clearly distinguished.
- [ ] Conflicting evidence and material counterarguments are addressed.
- [ ] No proprietary metrics or architecture have been invented.
- [ ] The technical section explains product-specific system behaviour rather than merely listing technologies or showing generic boxes.
- [ ] Core workflows are traced across clients, APIs, backend capabilities, data stores, external dependencies, state changes, and failure recovery.
- [ ] Data architecture, API contracts, search/ML, infrastructure, reliability, security, and observability are covered where material, or explicitly identified as unknown with a useful reference design.
- [ ] Tables, charts, and diagrams improve understanding and are properly sourced.
- [ ] The report contains meaningful analysis, not just feature descriptions.
- [ ] User likes, dislikes, recurring pain points, and positive value drivers are analysed from a suitably diverse evidence sample.
- [ ] Funnel stages and likely drop-off points are mapped, with measured data clearly separated from reported friction and hypotheses.
- [ ] Activation, retention, churn, cancellation, and reactivation are analysed where relevant.
- [ ] Product gaps are tied to specific user segments, jobs, evidence, consequences, and workarounds.
- [ ] Competitors and substitutes are benchmarked on meaningful workflows and current evidence.
- [ ] Recommendations explain how the product could compete and improve, with differentiation, trade-offs, validation plans, metrics, and guardrails.
- [ ] Reconstruction, if requested, is clearly marked as proposed.
- [ ] The DOCX is complete, readable, and structurally inspected.
- [ ] Any limitations in research or document inspection are disclosed.
- [ ] The chat response is concise and links to the correct generated file.
