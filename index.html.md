---
date_published: 2026-05-10
date_modified: 2026-05-10
canonical_url: https://ike.network/index.html
---

# IKE Network

The Integrated Knowledge Environment (IKE) is a community-driven platform for knowledge engineering. The IKE Network organization on GitHub hosts the Maven plugins, parent POMs, documentation toolchain, and reference projects that together form the IKE build and authoring ecosystem.

This page links each project to its source repository and to its generated Maven site. Source repositories live under the [IKE-Network](https://github.com/IKE-Network)[1] GitHub organization; generated sites publish under this domain at `[https://ike.network/<project>/](https://ike.network/<project>/)[2]`.

## [#projects](#projects)Projects

The IKE ecosystem is split into three layers — a tooling layer that provides the build plugins, a platform layer that provides the parent POM and BOM, and a reference layer of example consumers that demonstrate the conventions end-to-end.

### [#layer-1--tooling](#layer-1--tooling)Layer 1 — Tooling

| Project | Description |
| --- | --- |
| **IKE Tooling** [Repository](https://github.com/IKE-Network/ike-tooling)[3]  ·  [Generated Site](https://ike.network/ike-tooling/)[4] | Workspace management, release orchestration, build standards, and Maven plugins for IKE Network projects. Ships `ike-maven-plugin` (the `ike:*` goals — release prepare, BOM generation, site deploy, version upgrade), `ike-build-standards` (versioned Claude instruction files and build-config ZIPs), and related artifacts. First link in the release cascade. |
| **IKE Docs** [Repository](https://github.com/IKE-Network/ike-docs)[5]  ·  [Generated Site](https://ike.network/ike-docs/)[6] | The AsciiDoc documentation plumbing — `ike-doc-maven-plugin` (the `idoc:*` goals and the `ike-doc` custom packaging), `koncept-asciidoc-extension`, `minimal-fonts`, `docbook-xsl`, `ike-doc-resources`, and `semantic-linebreak`. Provides the multi-renderer HTML+PDF pipeline used by every IKE project that publishes documentation. |

### [#layer-2--platform](#layer-2--platform)Layer 2 — Platform

| Project | Description |
| --- | --- |
| **IKE Platform** [Repository](https://github.com/IKE-Network/ike-platform)[7]  ·  [Generated Site](https://ike.network/ike-platform/)[8] | The consumer-facing parent — `ike-parent` (the standard parent POM with Java 25 build conventions, GPG signing via Bouncy Castle, JaCoCo, the AsciiDoc documentation pipeline, and dependency-version management), `ike-bom` (the Maven BOM that pins every IKE-published artifact), and `ike-workspace-maven-plugin` (the `ws:*` goals that coordinate operations across an IKE multi-repo workspace). |

### [#layer-3--reference-projects](#layer-3--reference-projects)Layer 3 — Reference Projects

These projects exist to demonstrate and integration-test the tooling and platform layers. They are also the recommended starting point for new IKE consumers — copy their structure rather than building one from scratch.

| Project | Description |
| --- | --- |
| **example-project** [Repository](https://github.com/IKE-Network/example-project)[9]  ·  [Generated Site](https://ike.network/example-project/)[10] | Standalone code-plus-docs IKE reference project. Inherits `ike-parent` and demonstrates the full pattern — a JAR module, rendered AsciiDoc documentation, and BOM consumption — in one repository. The canonical template for an IKE library that ships both code and docs. |
| **doc-example** [Repository](https://github.com/IKE-Network/doc-example)[11]  ·  [Generated Site](https://ike.network/doc-example/)[12] | Standalone documentation-only IKE reference project. Inherits `ike-parent` and renders multi-renderer PDF and HTML through `ike-doc-maven-plugin`. The canonical template for a project whose deliverable is a published document rather than a JAR. |
| **ike-example-ws** [Repository](https://github.com/IKE-Network/ike-example-ws)[13]  ·  [Generated Site](https://ike.network/ike-example-ws/)[14] | Workspace-layer integration test harness. A `workspace.yaml` plus IT suite that exercises `ws:*` goals across `doc-example` and `example-project`. The canonical template for an IKE workspace aggregator that orchestrates multiple consumer repositories. |

## [#release-cascade](#release-cascade)Release Cascade

The three layers release in a fixed order — tooling first (so its plugin JARs are on Nexus before any consumer builds), then platform (whose `ike-parent` declares those plugins at literal versions via `<extensions>true</extensions>`), then the reference consumers and any downstream projects:

```
ike-tooling -> ike-docs -> ike-platform -> { example-project, doc-example } -> ike-example-ws
```

For the full diagnosis of why this ordering matters — in particular the Maven extension-plugin reactor-load cycle that drove the split of the original `ike-pipeline` monolith into the current three-repo shape — see [ike-issues#216](https://github.com/IKE-Network/ike-issues/issues/216)[15].

## [#quick-start](#quick-start)Quick Start

To inherit the IKE build conventions in a new project, declare `ike-parent` and IKE plugin groups, then build:

```
<parent>
    <groupId>network.ike.platform</groupId>
    <artifactId>ike-parent</artifactId>
    <version>22</version>
</parent>
```

Add the IKE plugin groups to `~/.m2/settings.xml` so the `ike:`, `ws:`, and `idoc:` prefix goals resolve:

```
<pluginGroups>
    <pluginGroup>network.ike.tooling</pluginGroup>
    <pluginGroup>network.ike.platform</pluginGroup>
    <pluginGroup>network.ike.docs</pluginGroup>
</pluginGroups>
```

For workspace operations across multiple IKE repositories, see the [ws:* Goal Reference](https://ike.network/ike-platform/ike-workspace-maven-plugin/ws-goals.html)[16] and the [Workspace Getting Started](https://ike.network/ike-platform/workspace-getting-started.html)[17] guide on the IKE Platform site.

## [#resources](#resources)Resources

| Resource | URL |
| --- | --- |
| GitHub organization | [https://github.com/IKE-Network](https://github.com/IKE-Network)[1] |
| Cross-project issue tracker | [https://github.com/IKE-Network/ike-issues](https://github.com/IKE-Network/ike-issues)[18] |
| Nexus artifact repository | [https://nexus.tinkar.org](https://nexus.tinkar.org)[19] |
| IKE Network landing | [https://ike.network](https://ike.network)[20] |
