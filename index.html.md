---
date_published: 2026-05-10
date_modified: 2026-05-10
canonical_url: https://ike.network/index.html
---

# IKE Network

The Integrated Knowledge Environment (IKE) is a community-driven platform for knowledge engineering.

## [#projects](#projects)Projects

## [#ike-docs](#ike-docs)IKE Docs

Documentation plumbing for the IKE Network. Hosts the ike-doc-maven-plugin (ike-doc packaging, AsciiDoc/render pipeline, PDF dispatch), the Koncept AsciiDoc extension, DocBook XSL + fonts, shared doc resources, and the semantic linebreak reformatter. Split from ike-pipeline to resolve the extensions=true reactor-load cycle. See IKE-Network/ike-issues#216.

| Version | 23 |
| --- | --- |
| Site | [ike.network/ike-docs](https://ike.network/ike-docs/)[1] |
| GitHub | [IKE-Network/ike-docs](https://github.com/IKE-Network/ike-docs)[2] |

#### [#modules](#modules)Modules

- ike-doc-resources
- minimal-fonts
- docbook-xsl
- koncept-asciidoc-extension
- ike-doc-maven-plugin
- semantic-linebreak

## [#ike-platform](#ike-platform)IKE Platform

Consumer-facing parent POM, BOM, and workspace management plugin for the IKE Network. External doc and code projects inherit from ike-parent (declared here); cross-repo workspace operations use ike-workspace-maven-plugin (ws:* goals). Consumes ike-docs as an external artifact — ike-parent declares ike-doc-maven-plugin with extensions=true, resolving from Nexus at project-load time. Split from the archived ike-pipeline; see IKE-Network/ike-issues#216.

| Version | 45 |
| --- | --- |
| Site | [ike.network/ike-platform](https://ike.network/ike-platform/)[3] |
| GitHub | [IKE-Network/ike-platform](https://github.com/IKE-Network/ike-platform)[4] |

#### [#modules_2](#modules_2)Modules

- ike-parent
- ike-workspace-maven-plugin
- ike-bom

## [#ike-tooling](#ike-tooling)IKE Tooling

Workspace management, release orchestration, gitflow workflows, and build-time utilities for IKE Network projects.

| Version | 166 |
| --- | --- |
| Site | [ike.network/ike-tooling](https://ike.network/ike-tooling/)[5] |
| GitHub | [IKE-Network/ike-tooling](https://github.com/IKE-Network/ike-tooling)[6] |

#### [#modules_3](#modules_3)Modules

- ike-build-standards
- ike-workspace-model
- ike-maven-plugin-support
- ike-maven-plugin
