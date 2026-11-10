# Awesome-SOC2-Iso-Enterprise-Data-Privacy-Controls

# Awesome SOC2 / ISO Enterprise Data Privacy Controls

> A curated list of top SOC 2 / ISO Enterprise Data Privacy Controls platforms — both SaaS/Hosted commercial solutions and open-source alternatives for compliance automation, privacy request fulfillment, and data governance.
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [Vanta](#vanta)
  - [Drata](#drata)
  - [Secureframe](#secureframe)
  - [OneTrust](#onetrust)
  - [TrustArc](#trustarc)
  - [DataGrail](#datagrail)
  - [BigID](#bigid)
  - [Securiti.ai](#securitiai)
- [Open-Source Software](#-open-source-software)
  - [Openlane](#openlane)
  - [Blackfyre](#blackfyre)
  - [CISO Assistant](#ciso-assistant)
  - [Fides (Ethyca)](#fides-ethyca)
  - [DSAR (inthhq)](#dsar-inthhq)
  - [privacy-dsar-mcp-server](#privacy-dsar-mcp-server)
  - [ConsentOS](#consentos)
  - [c15t](#c15t)
  - [tarteaucitron.js](#tarteaucitronjs)
- [Comparison at a Glance](#-comparison-at-a-glance)
- [Contributing](#-contributing)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted SOC 2 / ISO Enterprise Data Privacy Controls platforms. These are not open-source but are included as reference points for feature comparison.

### Vanta
**Type:** Compliance automation for SOC 2, ISO 27001, and more  
Vanta is the most widely recognized compliance automation platform, helping organizations achieve SOC 2, ISO 27001, HIPAA, and GDPR compliance through automated evidence collection, continuous monitoring, and vendor management. It is the primary commercial reference point for open-source alternatives like Openlane and Comp AI [citation:6][citation:12].

### Drata
**Type:** Compliance automation with continuous control monitoring  
Drata provides similar compliance automation capabilities to Vanta, with automated evidence collection, risk management, and policy templates. It is frequently cited alongside Vanta as the commercial benchmark that open-source projects aim to replace.

### Secureframe
**Type:** Compliance and security program automation  
Secureframe offers compliance automation with a focus on simplifying the audit process. It provides automated evidence collection, policy management, and integration with cloud infrastructure.

### OneTrust
**Type:** Privacy management and consent platform  
OneTrust is the dominant commercial privacy management platform, covering consent management, data mapping, privacy impact assessments, and vendor risk. It is the primary commercial reference for open-source consent management tools like ConsentOS and c15t [citation:10][citation:15].

### TrustArc
**Type:** Privacy compliance and certification  
TrustArc provides privacy compliance solutions including assessments, certifications, and ongoing monitoring. It is a long-standing commercial option for organizations needing formal privacy certifications.

### DataGrail
**Type:** Data privacy management with DSAR automation  
DataGrail specializes in data privacy management, with a focus on automating Data Subject Access Requests (DSARs), data mapping, and consent management. It is a direct commercial reference for open-source DSAR tools like Fides and the inthhq DSAR engine [citation:1][citation:5].

### BigID
**Type:** Data discovery and privacy intelligence  
BigID provides data discovery and classification for privacy compliance, helping organizations find and understand personal data across their systems. It is a commercial reference for open-source data governance tools.

### Securiti.ai
**Type:** Data privacy and governance platform  
Securiti.ai provides a unified platform for data privacy, security, and governance, with capabilities for data discovery, DSAR automation, and consent management.

---

## 🟩 Open-Source Software

Self-hosted, community-driven SOC 2 / ISO Enterprise Data Privacy Controls tools. The open-source ecosystem **splits** between **compliance automation platforms** (Openlane, Blackfyre, CISO Assistant) and **privacy engineering tools** (Fides, DSAR, ConsentOS).

### Openlane
**Stack:** Go / PostgreSQL / Redis / OpenFGA | **License:** Apache-2.0  
Openlane is the **most direct open-source alternative to Vanta, Drata, and Secureframe**, explicitly positioning itself as compliance automation for SOC 2, GDPR, ISO 27001, NIST 800-53, and more [citation:6][citation:8]. The core is developed entirely in the open, with security features like SSO and 2FA enforcement shipping in every module rather than sitting behind an enterprise tier [citation:6]. The stack runs on Go, PostgreSQL, Redis, and OpenFGA, avoiding the "pile of SaaS dependencies" that it criticizes in competitors [citation:6]. It includes a UI (openlane-ui), job queue (riverboat), and observability tools (beacon).  
**Best for:** Organizations wanting a genuinely open-source compliance automation platform with no enterprise feature gating, built on a modern Go stack.

### Blackfyre
**Stack:** Multi-cloud (AWS/Azure/GCP) / AI-assisted | **License:** Open Source  
Blackfyre is an open-source **multi-cloud compliance and security platform** that scans cloud infrastructure against **678 controls across 9 frameworks**, including SOC 2, ISO 27001, GDPR, HIPAA, PCI-DSS, and NIST 800-53 [citation:2]. Features include:
- 40+ SDK-based auditors plus Prowler and IaC scanning (Checkov/Semgrep/Bandit) 
- **AI-assisted analysis** (gap analysis, MITRE ATT&CK mapping, remediation suggestions) with graceful degradation to heuristics when no API key is configured 
- **Evidence vault** with SHA-256 content hashing and S3 Object Lock (WORM, COMPLIANCE mode) on AWS deployments 
- Multi-tenancy with Postgres row-level security, JWT + MFA, Google SSO, SAML, SCIM provisioning, and auditor-scoped access [citation:2]

Deploys via Docker Compose with localstack for local development, or in Codespaces with zero install [citation:2].  
**Best for:** Cloud-native organizations wanting to scan AWS/Azure/GCP against SOC 2 and ISO 27001 controls with AI-assisted remediation and tamper-evident evidence.

### CISO Assistant
**Stack:** Python / Django / PostgreSQL / S3 | **License:** Open Source  
CISO Assistant is an open-source **GRC (Governance, Risk, and Compliance)** platform supporting **30+ standards and frameworks** including SOC 2, ISO 27001, NIST CSF, GDPR, HIPAA, PCI DSS, NIS2, and DORA [citation:13]. It provides risk and audit management, with a Django backend and a frontend. Deployment requires PostgreSQL, optional S3 bucket for storage, and Huey for task running [citation:13].  
**Best for:** Organizations wanting a comprehensive open-source GRC platform with broad framework coverage beyond just SOC 2 and ISO 27001, accepting a more traditional Django-based deployment.

### Fides (Ethyca)
**Stack:** Python | **License:** Apache-2.0  
Fides is an open-source **privacy engineering platform** for managing the fulfillment of data privacy requests in your runtime environment, and the enforcement of privacy regulations in code [citation:1]. It supports GDPR, CCPA, and LGPD by default, plus ISO 19944. Key features include:
- End-to-end Data Subject Request automation 
- **Privacy-as-Code** for labeling system privacy characteristics 
- Compliance-minded data mapping 
- Auditing of stored PII throughout application systems [citation:1]

Fides is the most mature open-source DSAR automation tool, with 453 GitHub stars as of mid-2026 [citation:7].  
**Best for:** Engineering teams wanting to embed privacy request fulfillment and data mapping directly into their application runtime, with support for major privacy regulations.

### DSAR (inthhq)
**Stack:** TypeScript / Bun / Turbo | **License:** Apache-2.0  
DSAR is a **developer-first Data Subject Access Request engine** with a clean separation of authentication lanes: machine access via API keys/bearer tokens, and trusted host identity projection via `resolveTrustedRequestIdentity` [citation:5]. This keeps end-user login in the host product while DSAR focuses on tenant scoping and route authorization. It is a monorepo with a kitchen-sink example showing runtime auth wiring, and includes Unkey integration documentation [citation:5].  
**Best for:** Developers wanting a clean, API-driven DSAR engine to embed into their own product, with clear auth separation between machine access and end-user identity.

### privacy-dsar-mcp-server
**Stack:** Python | **License:** MIT  
privacy-dsar-mcp-server is an **MCP server for GDPR privacy compliance and DSAR management**, positioned as an open-source alternative to Transcend MCP [citation:11]. It provides tools for:
- Creating DSARs with automatic 30-day deadline tracking (GDPR Art. 12) 
- Listing DSARs sorted by urgency (overdue/critical first) 
- Checking GDPR compliance against 15 rules with A-F scoring 
- Registering data processing activities (Article 30 GDPR) 
- Privacy officer dashboard with open/overdue DSARs and action items [citation:11]

Data is stored locally at `~/.privacy_dsar_store.json` with no external services required [citation:11].  
**Best for:** Privacy officers and small teams wanting a lightweight, MCP-based DSAR tracker with GDPR compliance scoring, installable via pip and usable with Claude Desktop.

### ConsentOS
**Stack:** Python / FastAPI / Playwright / Docker | **License:** Elastic-2.0 (source-available)  
ConsentOS is a **privacy-first cookie consent management platform** positioned as a self-hosted alternative to OneTrust, Cookiebot, and CookieYes [citation:10]. It supports **IAB TCF v2.3, GPP v1, Google Consent Mode v2, GPC, and Shopify Customer Privacy API**. Features include:
- Auto-blocking of scripts, cookie writes, and storage API calls until consent is granted 
- Playwright-driven cookie scanner with auto-categorization against the Open Cookie Database (2,200+ patterns) 
- **Dark pattern detection** (pre-ticked boxes, missing reject buttons, button asymmetry) 
- Compliance engine with rules for GDPR, CNIL, CCPA/CPRA, ePrivacy, and LGPD 
- GeoIP-aware consent modes (opt-in for EU, opt-out for US-CA) [citation:10]

**Important licensing note:** ConsentOS is source-available under the Elastic License 2.0, not OSI-approved open source, which limits commercial reuse and redistribution [citation:10].  
**Best for:** Organizations wanting a feature-rich, self-hosted consent management platform with standards compliance and dark pattern detection, accepting the source-available licensing terms.

### c15t
**Stack:** TypeScript / Next.js | **License:** Open Source  
c15t is an open-source **consent management platform** that transforms privacy consent into a fully observable system [citation:15]. It provides a TypeScript-first SDK with automatic jurisdiction detection, a customizable consent banner, and support for managing third-party scripts based on user consent. It integrates with Next.js via a provider and supports pre-built helpers for Google Tag Manager, PostHog, and Meta Pixel [citation:15].  
**Best for:** Next.js and TypeScript developers wanting a modern, developer-friendly consent management SDK with automatic script blocking and jurisdiction detection.

### tarteaucitron.js
**Stack:** JavaScript | **License:** Open Source (MIT)  
tarteaucitron.js is a free, open-source **JavaScript consent manager** for adding a cookie consent banner to websites and letting visitors control third-party services [citation:4]. It provides the consent interface and service controls for a CMP setup, helping implement GDPR/RGPD consent requirements. Features include service-level preferences, consent-based loading (services blocked until permission granted), content placeholders, and **Google Consent Mode v2, Bing Consent Mode, and Piano Analytics Consent Mode** integrations [citation:4]. It is maintained by an independent French developer, with a paid Pro service offering automatic service detection and an online configuration dashboard.  
**Best for:** Web developers wanting a lightweight, self-hosted consent banner library with explicit service-level controls, without adopting a full CMP platform.

---

## 📊 Comparison at a Glance

| Software | License | Stack | SOC 2 / ISO | Privacy/DSAR | Consent Mgmt | Self-Hosted | Best For |
|----------|---------|-------|-------------|--------------|--------------|-------------|----------|
| **Vanta** | Proprietary | Cloud | ✅ | (Vendor) | ❌ | ❌ | Commercial compliance automation |
| **OneTrust** | Proprietary | Cloud | (Vendor) | ✅ | ✅ | ❌ | Commercial privacy suite |
| **Openlane** | Apache-2.0 | Go/Postgres | ✅ | (Vendor) | ❌ | ✅ | Open-source Vanta alternative |
| **Blackfyre** | Open Source | Multi-cloud | ✅ (678 controls) | (GDPR controls) | ❌ | ✅ | Cloud compliance scanning |
| **CISO Assistant** | Open Source | Python/Django | ✅ (30+ frameworks) | (GDPR) | ❌ | ✅ | Broad GRC platform |
| **Fides** | Apache-2.0 | Python | ❌ | ✅ DSAR + mapping | ❌ | ✅ | Privacy-as-code DSAR |
| **DSAR (inthhq)** | Apache-2.0 | TypeScript | ❌ | ✅ DSAR engine | ❌ | ✅ | Embeddable DSAR engine |
| **privacy-dsar-mcp** | MIT | Python | ❌ | ✅ DSAR + GDPR score | ❌ | ✅ (Local) | MCP-based DSAR tracker |
| **ConsentOS** | Elastic-2.0 | Python/FastAPI | ❌ | (GDPR rules) | ✅ TCF/GPP | ✅ | Self-hosted CMP + dark patterns |
| **c15t** | Open Source | TypeScript | ❌ | ❌ | ✅ | ✅ (SDK) | Next.js consent SDK |
| **tarteaucitron** | MIT | JavaScript | ❌ | ❌ | ✅ | ✅ (Library) | Lightweight consent banner |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source SOC 2 / ISO Enterprise Data Privacy Controls tool that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source (or clearly note if it is source-available but not OSI-approved, as with ConsentOS). Note that the open-source ecosystem **splits** between **compliance automation** (Openlane, Blackfyre, CISO Assistant) and **privacy engineering** (Fides, DSAR, ConsentOS, c15t, tarteaucitron). **Openlane** is the most direct Vanta/Drata alternative with no enterprise feature gating [citation:6]. **Blackfyre** offers the broadest framework coverage with AI-assisted cloud scanning and tamper-evident evidence [citation:2]. **Fides** is the most mature open-source DSAR automation platform, embedding privacy-as-code into application runtime [citation:1]. For consent management, **ConsentOS** offers the most feature-dense self-hosted CMP, though its Elastic license restricts commercial reuse [citation:10].

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
