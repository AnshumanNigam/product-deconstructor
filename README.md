# Product Deconstructor

**Reverse-engineer digital products. Understand their users, business models, technology, and competitive advantages. Discover how to build something better.**

Product Deconstructor is an AI Agent Skill that performs comprehensive product teardowns from simple prompts.

Give it a product name, such as `Teardown Spotify`, `Teardown YouTube`, or `Teardown Airbnb`. It independently researches the product, analyses its ecosystem, investigates its technology, identifies weaknesses and opportunities, and produces a structured report.

## What does it analyse?

### 1. Product and user experience
- Product positioning and value proposition
- Core features and product capabilities
- User personas and jobs to be done
- End-to-end user journeys and workflows
- UX strengths, friction points and usability issues
- Activation, engagement and retention

### 2. User intelligence
- What users love about the product
- Common complaints and frustrations
- Feature requests and unmet needs
- Reasons users abandon workflows
- Churn and switching factors
- Patterns in user reviews and community discussions

### 3. Funnel and growth analysis
- Acquisition and onboarding
- Activation and conversion
- User engagement and retention
- Drop-off points and friction
- Growth loops and network effects
- Distribution and acquisition channels

### 4. Business and economic analysis
- Revenue streams and monetisation
- Pricing strategy and packaging
- Business model and operating structure
- Cost drivers and unit economics
- Competitive positioning and defensibility
- Market opportunities and strategic risks

### 5. Technical deep dive
- System architecture and component breakdown
- Frontend and backend architecture
- Core services and service boundaries
- Database design and data relationships
- APIs, integrations and communication flows
- Search, ranking and recommendation systems
- AI/ML models and personalisation
- Cloud infrastructure and deployment
- Caching, queues and data pipelines
- Scalability, reliability and performance
- Security, privacy and observability

Technical analysis distinguishes publicly documented implementation details from inferred reference architectures. Proprietary internals are never presented as verified facts.

### 6. Competitive intelligence
- Direct and indirect competitors
- Feature and capability comparisons
- Pricing and monetisation comparisons
- UX and technology comparisons
- Competitor strengths and weaknesses
- Underserved customer segments
- Competitive vulnerabilities

### 7. Product gaps and opportunities
- Missing or underdeveloped capabilities
- Poor user experiences
- Technical limitations
- Pricing and monetisation weaknesses
- Operational inefficiencies
- Unmet customer needs
- Opportunities for differentiation

### 8. Recommendations
- Prioritised product improvements
- Opportunities to outperform competitors
- New features and capabilities
- Technical improvements
- Potential business model improvements
- Validation experiments and success metrics
- Short-, medium- and long-term roadmap

## Quick start

No lengthy prompt or detailed instructions required.

Simply ask your AI coding agent:

```text
Teardown Spotify
```

Other examples:

```text
Teardown YouTube
```

```text
Analyse Notion
```

```text
Reverse-engineer Airbnb
```

```text
Teardown ChatGPT
```

The skill automatically determines the relevant analytical dimensions based on the product category.

## Output

For substantial analyses, Product Deconstructor generates a structured DOCX report containing relevant:

- Executive summaries
- Analytical tables
- Competitive comparison matrices
- User journey diagrams
- System architecture diagrams
- Technical workflows
- Charts based on sourced quantitative evidence
- Product recommendations
- Opportunity assessments
- References and source notes

The goal is analytical depth and actionable insights, not simply generating a long document.

## Evidence and research standards

The skill distinguishes four types of findings:

| Classification | Meaning |
|---|---|
| Verified | Supported by reliable sources or direct product observation |
| Inferred | Reasoned interpretation based on available evidence |
| Unknown | Information that cannot be reliably established |
| Proposed | Recommendations for improving or rebuilding a product |

It does not invent internal metrics, proprietary architecture, user drop-off percentages, CAC, LTV or other undisclosed information.

It distinguishes observed user complaints from measured product analytics and hypotheses.

## Installation

### Codex

Clone this repository into your personal Codex skills directory:

```powershell
git clone https:/github.com/AnshumanNigam/product-deconstructor.git "$HOME\.agents\skills\product-deconstructor"
```

Alternatively, place the repository folder inside your project's:

```text
.agents/skills/product-deconstructor/
```

The resulting structure should be:

```text
product-deconstructor/
└── SKILL.md
```

Start a new Codex session if the skill is not discovered automatically.

### Manual installation

1. Download this repository.
2. Copy `SKILL.md` into a folder named `product-deconstructor`.
3. Place that folder in one of the supported Codex skill directories.

See the [official Codex Agent Skills documentation](https://learn.chatgpt.com/docs/build-skills) for additional installation information.

## Who is this for?

- Product managers
- Founders and entrepreneurs
- Software engineers
- Product designers
- Business analysts
- Market researchers
- Startup operators
- Students learning product and technology strategy

## Current status

**Version:** 2.2.0

**Status:** Experimental. Requires further execution testing across different product categories.

The skill is designed for broad product analysis, but output quality depends on available research sources, tools and product information.

## Contributing

Contributions, suggestions, improvements and issue reports are welcome.

See [CONTRIBUTING.md](CONTRIBUTING.md) for contribution guidelines.

## License

This project is intended to be released under the MIT License. See [LICENSE](LICENSE) once added.

---

**Built to help people understand products deeply, identify opportunities, and think beyond existing solutions.**
