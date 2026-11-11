# FD CODE

FD CODE is a customised version of [T3 Code](https://github.com/pingdotgg/t3code), focused on using coding agents with local context and connected tools. The base application is upstream T3 Code; this write-up describes the additions documented in [my repository](https://github.com/faheemdehalvi/fd-code).

## What the project adds

The repository describes General chat, local Laya routing, Brain continuity, provider handoffs and ARTsie integration. The practical question behind those additions is how to keep the information and tools needed for a task available as the working session changes.

That involves more than selecting a model. A useful handoff needs the task, relevant decisions, current state and remaining work. The person operating the system also needs to understand which tools are connected and what an agent is allowed to do.

## Engineering decisions worth explaining

- Context retrieval and session continuity need explicit scope. The repository distinguishes built-in session continuity from the separate local Brain knowledge desk, which is not distributed.
- An integration needs a usable entry point. FD CODE connects ARTsie tool discovery and operations to the coding-agent environment.
- A fork should identify its foundation. The README separates the customised build from upstream T3 Code documentation and credits the upstream application.

## Evidence and current limits

This note follows the public README reviewed on 11 November 2026 at [source snapshot 2acda61](https://github.com/faheemdehalvi/fd-code/tree/2acda619befd54438dedcb9b18d1348f1889b5b4). It describes intended capabilities, rather than reporting a new performance evaluation.

The README currently includes an outdated `npx fd-code@latest` reference; that package returned404 when checked on 11 November. Use the repository's release documentation and inspect its current state before installation. A local correction has been prepared. Windows and macOS setup were not re-tested for this write-up.

## A useful next demonstration

Take one small task, record the required context, make a provider handoff, and check which facts and instructions remain available. Report the versions, supplied context and observed result. That experiment is proposed; this note does not claim it has been completed.

[Repository](https://github.com/faheemdehalvi/fd-code) · [Upstream T3 Code](https://github.com/pingdotgg/t3code) · [My writing](https://faheemdehalvi.github.io/)
