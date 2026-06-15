# DocusaurOps

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://app-docusaurops-root-qlrnl.azurewebsites.net/img/logo-light.svg">
  <source media="(prefers-color-scheme: light)" srcset="https://app-docusaurops-root-qlrnl.azurewebsites.net/img/docusaurops_logo_public.svg">
  <img alt="DocusaurOps Logo" src="https://app-docusaurops-root-qlrnl.azurewebsites.net/img/logo-light.svg">
</picture>

> Transform Your Organizational Knowledge Into a Strategic Asset

[![Get Started with DocusaurOps](https://img.shields.io/badge/Get%20Started%20with%20DocusaurOps-Open%20Portal-0A66C2?style=for-the-badge)](https://app-docusaurops-root-qlrnl.azurewebsites.net/)
[![Test it by yourself](https://img.shields.io/badge/Test%20it%20by%20yourself-Open%20Playground-2EA44F?style=for-the-badge)](https://app-docusaurops-root-qlrnl.azurewebsites.net/docs/playground)

DocusaurOps is a documentation automation platform that unifies infrastructure automation, docs‑as‑code templates, and Microsoft WorkIQ to eliminate the overhead of documentation setup and management. It maintains documentation continuity across the entire project lifecycle and integrates with whatever tools or formats your organization already uses—GitHub, SharePoint, or any other platform—so multi‑disciplinary teams always work with the latest, most accurate information aligned with what’s actually implemented.

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://app-docusaurops-root-qlrnl.azurewebsites.net/img/docusaurops_lifecycle.png">
  <source media="(prefers-color-scheme: light)" srcset="https://app-docusaurops-root-qlrnl.azurewebsites.net/img/docusaurops_lifecycle_light.png">
  <img alt="DocusaurOps Lifecycle" src="https://app-docusaurops-root-qlrnl.azurewebsites.net/img/docusaurops_lifecycle_light.png">
</picture>

The solution is first of all an architecture pattern that any company can adopt to rationalize technical documentation across teams and projects — as a fully self-service experience. It is also a foundation for a customizable AI-SDLC approach, where teams can write their own skills using the same underlying techniques.



## At a glance

- 🎬 Demo Video:

  [![DocusaurOps Demo Video](https://img.youtube.com/vi/lJwHwJmwiQw/hqdefault.jpg)](https://youtu.be/lJwHwJmwiQw)

- 🔗 Public GitHub Repository: [https://github.com/FranckyC/agents-league-docusaurops](https://github.com/FranckyC/agents-league-docusaurops)
- 🌐 Live Documentation Portal: [https://app-docusaurops-root-qlrnl.azurewebsites.net](https://app-docusaurops-root-qlrnl.azurewebsites.net)
- 🪣 Test the documentation setup process by yourself using our plugin and playground environment: [https://app-docusaurops-root-qlrnl.azurewebsites.net/docs/playground](https://app-docusaurops-root-qlrnl.azurewebsites.net/docs/playground)



## Project Description

### Problem Solved

In most organizations, technical knowledge is everywhere and nowhere at the same time. Documentation lives across disconnected SharePoint sites, repositories, personal drives, outdated PDFs, Word files, and Markdown pages that are hard to discover.

This creates recurring issues:

- Low discoverability of critical information
- Inconsistent documentation formats across teams
- No reliable single source of truth
- Growing documentation debt over time
- Knowledge loss when people leave the organization
- Teams rebuilding work that already exists

Documentation then becomes a last-minute task instead of an operational asset.

### Imagine Documentation That Works for You

DocusaurOps helps organizations establish a practical docs-as-code strategy that teams can adopt quickly:

- Centralized, searchable documentation accessible from where developers already work (VS Code and CLI)
- Faster knowledge discovery without guesswork
- Structured and maintainable documentation over time
- Better alignment between engineering, business analysts, security, and stakeholders

### How DocusaurOps Makes This Real

1. Get started in minutes
Install the GitHub Copilot plugin and ask the agent to set up documentation for your project.

```bash
copilot -p "Setup documentation for my project 'XYZ'"
```

DocusaurOps scaffolds the documentation site, deploys it, and wires CI/CD automation, reducing manual setup effort.

2. Search the whole organization
Each DocusaurOps site is published through a unified entry point and indexed via Copilot Connector, enabling broad discoverability.

3. Ask the agent directly
Teams can query indexed knowledge from the DocusaurOps agent in Copilot CLI and VS Code for faster, contextual answers.

4. Keep everyone aligned
The same documentation baseline supports developers and non-technical stakeholders, improving traceability and shared understanding.

### Features and Functionality

- ⚡ **Docs setup and upgrade automation** via the `/docs-setup` skill.
- 🔍 **Cross-project documentation Q&A** via the `/docs-ask` skill.
- 📋 **Requirements-to-spec workflow** via the `/docs-specs` skill.
- ☁️ **Azure deployment assets** for core and site resources (Bicep + PowerShell).
- 📚 **Docusaurus portal** for a structured, searchable documentation experience.
- 🤖 **Copilot-ready plugin packaging** for VS Code Chat and GitHub Copilot CLI.

### Technologies Used

| Component | Role |
|-----------|------|
| **GitHub Copilot plugin** | Available in VS Code Chat and GitHub Copilot CLI |
| **Azure Application Gateway** | Routes incoming requests to the right documentation site. This is where the aggregation takes place. |
| **Docusaurus** | Static site generator enabling a documentation-as-code approach |
| **GitHub Actions & reusable workflows** | Automates deployment end-to-end through CI/CD pipelines |
| **Copilot Connector** | Indexes all sites for AI-powered search (Enterprise Websites) |
| **WorkIQ** | Reads and writes Word documents through Microsft 365 remote WorkIQ Word MCP Server + WorkIQ CLI to retrieve content from the Copilot connector. |

## Architecture Diagram

DocusaurOps is an architecture pattern that any company can adopt to rationalize technical documentation across teams and projects as a fully self-service experience. It is also a foundation for a customizable AI-SDLC approach, where teams can write their own skills using the same underlying techniques.

### Key Insight

One of the goals of this solution is to demonstrate what it takes — from an architectural standpoint — for an AI-powered solution to be truly valuable, and how all components must work together to form a coherent whole that translates into a real organizational strategy, not just a standalone fancy agent.

The architecture is designed to be modular and extensible, allowing new skills and capabilities to be added over time.

---

## 📖 Documentation Setup Workflow

![DocusaurOps - Documentation Platform skills Architecture](https://app-docusaurops-root-qlrnl.azurewebsites.net/img/docusaurops_docs_architecture_white_bg.png)

### How Documentation Sites Get Created and Deployed

**1. Install the plugin**

Developers install the DocusaurOps plugin from their company marketplace — a dedicated GitHub repository configured to host the plugin definition. The plugin works in both VS Code Chat and GitHub Copilot CLI, so developers can choose the experience that suits them best.

**2. Initialize a new documentation site**

From the plugin, a developer triggers the "Setup documentation" skill, providing basic information like project name and desired URL slug. The plugin takes care of the rest.

Using the GitHub CLI and the developer's own credentials, the `/docs-setup` skill clones the latest documentation structure from a dedicated template repository. This separation of template repository from plugin means:
- The template can be updated independently, without touching the plugin
- Changes are tracked with full history and clear diffs
- Migration paths are embedded directly in the template

An environment file (`.env.docusaurops`) is generated containing all deployment metadata (site name, slug, description, contact information, etc.), with all placeholder values replaced automatically.

**3. Write, preview, and deploy**

Developers write documentation locally using the Docusaurus structure and preview it with provided commands. When they push to the repository, the `deploy-docs.yml` workflow triggers and calls the reusable `deploy_site.yml` workflow, which handles:
- Configuring Application Gateway backend pools and path rules
- Configuring authentication on the new app
- Deploying site content from the repository

**No credentials or variables need to be set up by the developer** — everything is resolved automatically. This is where DocusaurOps truly shines as a self-service solution: deployment complexity is completely abstracted away, making it accessible to any team regardless of DevOps expertise.

**4. Site goes live and gets indexed**

The new site is published under the root URL `https://docs.my-company.com/{site_slug}` and automatically indexed by the Microsoft "Enterprise Websites" Copilot Connector, using a dynamically generated `sitemap.xml` file from the root web application.

Using a single URL for all documentation sites allows the organization to have a unified, searchable knowledge base without indexing every GitHub repository individually. DocusaurOps scales organically as teams create their sites.

**5. Searchable across the entire company**

Using the `/docs-ask` skill and WorkIQ CLI, developers can ask questions across all projects where documentation exists — *"How was feature XYZ implemented in project ABC?"* — creating a mesh of shared knowledge across the entire organization. The agent can even proactively suggest relevant documentation based on developer context (SharePoint sites, email, etc.).

### The Virtuous Cycle

The more teams adopt the platform, the richer the shared knowledge becomes. Content added by one team becomes a reference for others, continuously improving quality across the organization — organically.

---

## ✅ Compliance & Traceability Workflow

![DocusaurOps - Compliance & traceability skills Architecture](https://app-docusaurops-root-qlrnl.azurewebsites.net/img/docusaurops_docs-generation_architecture_white_bg.png)

Documentation is not just about explaining how a solution works — it is also a compliance and traceability artifact. DocusaurOps addresses a common organizational challenge: **keeping formal documents from non-technical stakeholders (business analysts, product owners, etc.) in sync with the actual implementation**.

### Turn Requirements Into Workable Issues

Business analysts or product owners often produce requirement documents that lack enough detail for technical teams. This workflow bridges the gap by transforming raw requirements into structured, actionable GitHub issues.

**1. Trigger the command**

A developer triggers the "Generate specifications" command from the plugin, pointing to a business requirement document in SharePoint or OneDrive (e.g., a Word .docx file).

**2. Extract and align requirements**

The plugin uses the WorkIQ Word MCP server to read the document and format its content according to a specification template. If information is missing, the plugin adds comments directly in the Word document so the analyst can respond. This back-and-forth continues until requirements are complete enough to generate workable specifications.

**3. Create GitHub issues**

The finalized specifications are created as issues in the GitHub project associated with the repository — ready for the team to plan and implement.

## 👤 Author

**Franck Cornu**

- 🐙 GitHub: [https://github.com/FranckyC](https://github.com/FranckyC)
- 💼 LinkedIn: [https://www.linkedin.com/in/franckcornu](https://www.linkedin.com/in/franckcornu)