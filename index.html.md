---
date_published: 2026-05-10
date_modified: 2026-05-10
canonical_url: https://ike.network/index.html
---

# IKE Network

The IKE Network (Integrated Knowledge Exchange) is a sociotechnical fabric where knowledge compounds.

## [#projects](#projects)Projects

## [#ike-documentation-example](#ike-documentation-example)IKE Documentation Example

Documentation-only project demonstrating the IKE AsciiDoc pipeline. Exercises all diagram types, Koncept macros, typography, and layout features across all 6 PDF renderers.

| Version | 30 |
| --- | --- |
| Site | [ike.network/doc-example](https://ike.network/doc-example/)[1] |
| GitHub | [IKE-Network/doc-example](https://github.com/IKE-Network/doc-example)[2] |

## [#ike-example-project](#ike-example-project)IKE Example Project

Example Java project demonstrating IKE documentation pipeline integration with Java source, tests, and Koncept macros.

| Version | 30 |
| --- | --- |
| Site | [ike.network/example-project](https://ike.network/example-project/)[3] |
| GitHub | [IKE-Network/example-project](https://github.com/IKE-Network/example-project)[4] |

## [#ike-base-parent](#ike-base-parent)IKE Base Parent

[https://central.sonatype.com/artifact/network.ike/ike-base-parent](https://central.sonatype.com/artifact/network.ike/ike-base-parent)[5]

Tier 0 foundation parent for the IKE Network — the apex of the parent inheritance forest, inherited by ike-tooling, ike-docs, and ike-platform. Carries shared publishing metadata, GPG signing, and Maven Central publishing configuration.

| Version | 1 |
| --- | --- |
| Site | [ike.network/ike-base-parent](https://ike.network/ike-base-parent/)[6] |
| GitHub | [IKE-Network/ike-base-parent](https://github.com/IKE-Network/ike-base-parent)[7] |

## [#ike-docs](#ike-docs)IKE Docs

Documentation plumbing for the IKE Network. Hosts the ike-doc-maven-plugin (ike-doc packaging, AsciiDoc/render pipeline, PDF dispatch), the Koncept AsciiDoc extension, DocBook XSL + fonts, shared doc resources, and the semantic linebreak reformatter. Split from ike-pipeline to resolve the extensions=true reactor-load cycle. See IKE-Network/ike-issues#216.

| Version | 45 |
| --- | --- |
| Site | [ike.network/ike-docs](https://ike.network/ike-docs/)[8] |
| GitHub | [IKE-Network/ike-docs](https://github.com/IKE-Network/ike-docs)[9] |

#### [#modules](#modules)Modules

- ike-doc-resources
- minimal-fonts
- docbook-xsl
- koncept-asciidoc-extension
- ike-doc-maven-plugin
- semantic-linebreak

## [#ike-example-integration-test-harness](#ike-example-integration-test-harness)IKE Example Integration Test Harness

End-to-end smoke tests that exercise the IKE Network release cascade as external consumers would. Each IT case clones the intended usage pattern (doc-only project, java + docs, BOM import, ws:create scaffold) in a fresh Maven environment and asserts that the build succeeds and produces the expected artifacts.

| Version | 22 |
| --- | --- |
| Site | [ike.network/ike-example-its](https://ike.network/ike-example-its/)[10] |
| GitHub | [IKE-Network/ike-example-its](https://github.com/IKE-Network/ike-example-its)[11] |

## [#ike-example-workspace](#ike-example-workspace)IKE Example Workspace

| Version | 21 |
| --- | --- |
| Site | [ike.network/ike-example-ws](https://ike.network/ike-example-ws/)[12] |
| GitHub | [IKE-Network/ike-example-ws](https://github.com/IKE-Network/ike-example-ws)[13] |

#### [#modules_2](#modules_2)Modules

- doc-example
- example-project
- its

## [#ike-platform](#ike-platform)IKE Platform

[https://central.sonatype.com/artifact/network.ike.platform/ike-platform](https://central.sonatype.com/artifact/network.ike.platform/ike-platform)[14]

Consumer-facing parent POM, BOM, and workspace management plugin for the IKE Network. External doc and code projects inherit from ike-parent (declared here); cross-repo workspace operations use ike-workspace-maven-plugin (ws:* goals). Consumes ike-docs as an external artifact — ike-parent declares ike-doc-maven-plugin with extensions=true, resolving from Nexus at project-load time. Split from the archived ike-pipeline; see IKE-Network/ike-issues#216.

| Version | 72 |
| --- | --- |
| Site | [ike.network/ike-platform](https://ike.network/ike-platform/)[15] |
| GitHub | [IKE-Network/ike-platform](https://github.com/IKE-Network/ike-platform)[16] |

#### [#modules_3](#modules_3)Modules

- ike-parent
- ike-workspace-maven-plugin
- ike-bom

## [#ike-tooling](#ike-tooling)IKE Tooling

[https://central.sonatype.com/artifact/network.ike.tooling/ike-tooling](https://central.sonatype.com/artifact/network.ike.tooling/ike-tooling)[17]

Workspace management, release orchestration, gitflow workflows, and build-time utilities for IKE Network projects.

| Version | 188 |
| --- | --- |
| Site | [ike.network/ike-tooling](https://ike.network/ike-tooling/)[18] |
| GitHub | [IKE-Network/ike-tooling](https://github.com/IKE-Network/ike-tooling)[19] |

#### [#modules_4](#modules_4)Modules

- ike-build-standards
- ike-workspace-model
- ike-maven-plugin-support
- ike-maven-plugin
