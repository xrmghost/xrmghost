<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="./assets/XG_Audiowide_transparent_negative.svg">
    <source media="(prefers-color-scheme: light)" srcset="./assets/XG_Audiowide_transparent.svg">
    <img alt="Xrm Ghost" src="./assets/XG_Audiowide_transparent_negative.svg" width="300" />
  </picture>
</p>


# Xrmghost

> Plugins that pass on your machine, not just in a sandbox.

You're on GitHub, looking at the `xrmghost/xrmghost` repository — this is the product's home base in the org, and the right place to start if you landed here first. Xrmghost lets your AI agent write Dataverse plugins and Custom APIs, then proves they work by running them against a simulated environment on your own machine, before anything touches a real deploy.

---

## Why a simulated Dataverse beats a shared sandbox

A shared cloud sandbox tells you what broke only after you've already waited for a deploy — and by then the answer is buried in trace logs, shared by whoever else is using the same environment. Xrmghost skips that wait: the plugin executes locally, against a faithful simulation of the platform, so the failure shows up in seconds, on data you control, with nobody else's changes in the way.

## The agent does the loop, you review the result

You (or your agent) write the plugin or Custom API. The agent invokes Xrmghost as a skill to run it locally, reads the result, and fixes what's wrong — wrong field name, missing security role, an edge case nobody wrote a test for. That cycle repeats without you touching a deploy pipeline. What lands on your desk for review is code that has already been proven to run.

## What's public, what isn't

The core engine stays closed for now, but the pieces you can read, reference, or build against are public and split by concern:

| Repository | What you'll find there |
|---|---|
| **[xrmghost-docs](https://github.com/xrmghost/xrmghost-docs)** | Source of the documentation site — install steps, CLI reference, architecture notes. |
| **[xrmghost-skills](https://github.com/xrmghost/xrmghost-skills)** | The Agent Skills that teach Claude Code, Copilot, Codex, and others to drive the local run/debug loop. |
| **[xrmghost-attributes](https://github.com/xrmghost/xrmghost-attributes)** | The `.NET` attribute library plugins are decorated with — usable standalone, no other Xrmghost component required. |
| **[.github](https://github.com/xrmghost/.github)** | The org-wide profile — a shorter map of the whole organization if this repo isn't where you want to be. |
| **[XrmGhost.Cli](https://www.nuget.org/packages/XrmGhost.Cli)** | The dotnet tool you actually install — `dotnet tool install -g XrmGhost.Cli` gets you the `xg` command line without cloning anything. |
| **[XrmGhost.Attributes](https://www.nuget.org/packages/XrmGhost.Attributes)** | Prebuilt NuGet package for the attribute library above — pull it into your plugin project directly instead of building the source repo yourself. |

## Go deeper

- Full install and CLI walkthrough: **[docs.xrmghost.tech](https://docs.xrmghost.tech)**
- Product overview and pricing: **[www.xrmghost.tech](https://www.xrmghost.tech)**

---

© 2026 Xrmghost. All rights reserved.
