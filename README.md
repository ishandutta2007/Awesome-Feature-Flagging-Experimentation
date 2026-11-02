# Awesome-Feature-Flagging-Experimentation

# Awesome Feature Flagging & Experimentation

> A curated list of top Feature Flagging and Experimentation platforms — both SaaS/Hosted commercial solutions and open-source alternatives for self-hosted feature management and A/B testing.  
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [LaunchDarkly](#launchdarkly)
  - [Statsig](#statsig)
  - [Optimizely Feature Experimentation](#optimizely-feature-experimentation)
  - [Split (Harness)](#split-harness)
  - [ConfigCat](#configcat)
  - [CloudBees Feature Management](#cloudbees-feature-management)
- [Open-Source Software](#-open-source-software)
  - [Flagsmith](#flagsmith)
  - [GrowthBook](#growthbook)
  - [Unleash](#unleash)
  - [PostHog](#posthog)
  - [GO Feature Flag](#go-feature-flag)
  - [FeatureProbe](#featureprobe)
  - [Bucketeer](#bucketeer)
- [Comparison at a Glance](#-comparison-at-a-glance)
- [Contributing](#-contributing)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted feature flagging and experimentation platforms. These are not open-source but are included as reference points for feature comparison.

### LaunchDarkly
**Type:** Enterprise feature management  
The category-defining incumbent with the deepest governance, audit workflows, and enterprise security posture. Broadest official SDK matrix and battle-tested at extreme scale (Atlassian, IBM, NBC). Pricing has escalated meaningfully; MAU-based pricing creates surprise bills for consumer apps, and six-figure renewals are standard at the 200+ engineer band [citation:1]. APIbenchmarks rates LaunchDarkly highest overall (ABI 91.1, grade A) for documentation, reliability, and ecosystem [citation:7].  
**Best for:** Large engineering organizations with regulated delivery processes and a need for mature release governance.

### Statsig
**Type:** AI-driven flags + experimentation + analytics  
Founded by ex-Facebook VP of Engineering, Statsig bundles feature flags, A/B testing, product analytics, session replay, and warehouse-native experimentation in a single evaluation API. Notable customers include Notion, OpenAI, Atlassian, Microsoft, Figma, and Brex. Free tier covers up to 1M events per month. Governance and audit features are less mature than LaunchDarkly at Fortune 500 tier [citation:1].  
**Best for:** Teams wanting an all-in-one flags + experiments + analytics platform with a generous free tier.

### Optimizely Feature Experimentation
**Type:** Server-side flags + experimentation  
Formerly Optimizely Full Stack, distinct from Optimizely Web (client-side A/B testing). Known for the deepest statistical experimentation engine alongside Statsig and Split. Strong fit for organizations already running Optimizely Web. Pricing is enterprise-only and opaque; standalone-flag buyers often find it uncompetitive against LaunchDarkly or Statsig [citation:1].  
**Best for:** Marketing-anchored organizations already in the Optimizely ecosystem.

### Split (Harness)
**Type:** Feature flags + experimentation (now Harness FME)  
Acquired by Harness in February 2024. Historically experimentation-first, with mature server-side flagging and strong impact measurement. Now bundled into the Harness Software Delivery Platform. Post-acquisition product direction has been mixed; standalone customers report slower velocity, and pricing is increasingly tied to Harness platform deals [citation:1].  
**Best for:** Teams already using Harness for CI/CD wanting integrated flags and experimentation.

### ConfigCat
**Type:** Simple, predictable feature flags  
Pricing is based solely on config downloads (not seats, not MAU), making it highly predictable for teams. Forever Free plan includes ~5 million downloads/month with all features available. No per-seat charges; unlimited developers. ConfigCat explicitly positions itself as a simpler, more predictable alternative to LaunchDarkly's MAU + service connection pricing model .  
**Best for:** Teams wanting straightforward flag management with transparent, usage-based pricing and no seat fees.

### CloudBees Feature Management
**Type:** Enterprise feature management  
Part of the CloudBees DevOps platform, offering feature flags with A/B testing, gradual rollouts, automated rollbacks, and governance. Supports both cloud and on-premise deployments, making it suitable for regulated industries (government, finance, healthcare) with hybrid environments [citation:6][citation:12].  
**Best for:** Enterprises needing feature flags tightly integrated with CI/CD and on-premise deployment options.

---

## 🟩 Open-Source Software

Self-hosted, community-driven feature flagging and experimentation tools. All listed projects offer source code you can deploy on your own infrastructure.

### Flagsmith
**Stack:** Python / Django / PostgreSQL | **License:** BSD-3-Clause (open core)  
Offers feature flags, remote config, and segmentation with a focus on governance and self-hosting for regulated environments. Maintains vendor-maintained OpenFeature providers. Core functionality stays open, including flags, remote config, segmentation, basic A/B testing, and 15+ SDKs. Supports Docker, Kubernetes/Helm, on-prem, and air-gapped deployments. Cloud pricing is transparent (Free $0, Start-Up $40/mo, Scale-Up $250/mo). Advanced governance and SSO are gated to paid Enterprise [citation:2][citation:14].  
**Best for:** Organizations prioritizing compliance and genuine self-hosting with a permissive license.

### GrowthBook
**Stack:** TypeScript / MongoDB (warehouse-native) | **License:** MIT core (open core)  
Built around experimentation: connects to your data warehouse (BigQuery, Snowflake, Databricks) and runs Bayesian/frequentist analysis without ingesting a copy of your events. Deepest experimentation stats engine among open-source flag tools: CUPED, sequential testing, Bayesian analysis, multi-arm bandits, SRM checks. 24 SDKs. Self-hosted open-source edition runs unlimited users at $0, but requires an instrumented warehouse and statistical understanding. Visual editor, bandits, SSO, and SCIM are gated to Enterprise [citation:2][citation:14].  
**Best for:** Data teams whose primary need is rigorous warehouse-native experimentation tied to feature delivery.

### Unleash
**Stack:** Node.js / PostgreSQL | **License:** Apache-2.0 core (open core)  
One of the most mature open-source feature management platforms, with an 11-year track record, ~13.7k GitHub stars, and G2 4.7 across 122 reviews. Full admin dashboard, 25+ SDKs, activation strategies, gradual rollouts, kill switches, canary releases, and Unleash Edge for low-latency evaluation. Genuinely air-gapped self-hosting possible. Advanced RBAC, SSO, and SCIM are gated to paid Enterprise. Self-hosting requires PostgreSQL [citation:2][citation:14].  
**Best for:** Teams wanting a battle-tested, feature-rich self-hosted platform with a strong operational UI.

### PostHog
**Stack:** Python / ClickHouse / PostgreSQL / Redis | **License:** MIT core (open core)  
Bundles product analytics, session replay, experiments, and feature flags. If you already run PostHog for analytics, its flags and experiments are tightly integrated with your data. OpenFeature support is third-party (community) and not vendor-maintained. Self-hosting is heavy — requires PostgreSQL, ClickHouse, and Redis — and PostHog officially steers most users to its cloud offering, with self-hosting docs stating no guarantees and users assume all risk [citation:2].  
**Best for:** Teams already invested in PostHog's analytics suite who want flags and experiments in the same platform.

### GO Feature Flag
**Stack:** Go | **License:** Open Source  
A simple, complete, and lightweight self-hosted cloud-native feature flag solution built on OpenFeature. 100% open source with no open-core gating. Designed for teams that want a minimal, Go-based flag evaluation service without the overhead of a larger platform. Listed among GitHub's OpenFeature topic repositories as a self-hosted, OpenFeature-compatible control plane [citation:3].  
**Best for:** Go-centric teams wanting a lightweight, fully open-source OpenFeature-native solution.

### FeatureProbe
**Stack:** (Check repository) | **License:** Open Source  
An open-source feature management service providing feature flags, gradual rollouts, and A/B experimentation with a visual management interface. Listed in GitHub's feature-flags topic as a full-featured open-source alternative [citation:15].  
**Best for:** Teams wanting a visual feature management platform with experimentation built in.

### Bucketeer
**Stack:** (Check repository) | **License:** Open Source  
A Japanese open-source feature flag platform (from CyberAgent) with an official OpenFeature provider. Frequently cited in Japanese enterprise contexts and among the OSS camp alongside GrowthBook, Unleash, and Flagsmith for self-hosted scenarios [citation:8].  
**Best for:** Teams in the Japanese market or those wanting an OpenFeature-native OSS alternative.

---

## 📊 Comparison at a Glance

| Software | License | Type | Self-Hosted | Experimentation | Best For |
|----------|---------|------|-------------|-----------------|----------|
| **LaunchDarkly** | Proprietary | Enterprise flags | ❌ | Strong | Enterprise governance |
| **Statsig** | Proprietary | Flags + analytics | ❌ | Strong | All-in-one + free tier |
| **Optimizely FE** | Proprietary | Server-side experiments | ❌ | Deepest stats | Optimizely ecosystem |
| **Split (Harness)** | Proprietary | Flags + experiments | ❌ | Strong | Harness CI/CD users |
| **ConfigCat** | Proprietary | Simple flags | ❌ | Basic | Predictable pricing |
| **CloudBees FM** | Proprietary | Enterprise flags | ✅ (on-prem) | Moderate | Regulated hybrid envs |
| **Flagsmith** | BSD-3 (core) | Flags + remote config | ✅ | Basic | Compliance + self-host |
| **GrowthBook** | MIT (core) | Warehouse-native experiments | ✅ | Deepest OSS stats | Data-team experimentation |
| **Unleash** | Apache-2.0 (core) | Mature OSS flags | ✅ | Moderate | Battle-tested self-host |
| **PostHog** | MIT (core) | All-in-one analytics | ✅ (heavy) | Moderate | Existing PostHog users |
| **GO Feature Flag** | Open Source | Lightweight OSS | ✅ | Basic | Go / OpenFeature native |
| **FeatureProbe** | Open Source | Visual OSS platform | ✅ | Built-in | Visual management |
| **Bucketeer** | Open Source | OSS + OpenFeature | ✅ | (Check) | OpenFeature native |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source feature flagging or experimentation tool that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source.

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
