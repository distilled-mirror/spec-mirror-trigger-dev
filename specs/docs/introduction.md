> ## Documentation Index
> Fetch the complete documentation index at: https://trigger.dev/docs/llms.txt
> Use this file to discover all available pages before exploring further.

# Trigger.dev docs

> Build and run durable AI agents and workflows in TypeScript. Long-running tasks with retries, queues, observability, and elastic scaling. Open source and self-hostable.

> **[Quick start](/docs/quick-start.md)**
>
> Go from zero to your first task in 3 minutes.

> **[Build AI agents](/docs/guides/ai-agents/overview.md)**
>
> Agent patterns, worked examples, and the tools to run them in production.

> **[AI coding assistants](/docs/building-with-ai.md)**
>
> Let Claude Code, Cursor and Windsurf write correct Trigger.dev code with the MCP server, Skills and rules.

> **[Guides & examples](/docs/guides/introduction.md)**
>
> Frameworks like Next.js, worked example projects, and step-by-step how-to guides.

## Set up with AI

Copy this prompt into your AI coding assistant from your app's directory:

```text theme={"theme":"css-variables"}
Bootstrap a Trigger.dev project: trigger.dev/SKILL.md
```

Your agent guides you through login, choosing or creating an organization and project, and running your first task locally. You authorize login yourself, and the agent asks when a choice is ambiguous.

[Read the full setup instructions](https://trigger.dev/SKILL.md) before running.

## What is Trigger.dev?

Trigger.dev is the open source platform for building and running durable AI agents and workflows in TypeScript. Run them for hours, configure automatic retries, control concurrency, and manage queues. There's no execution timeout, and no queue or worker infrastructure for you to build.

You write agents and tasks in your existing codebase using our CLI and SDK, and get durable execution, queues, waits, full tracing, and elastic scaling without building any of it yourself.

Trigger.dev's core is Apache-2.0 licensed, a genuine OSI license. [Self-host it](/docs/self-hosting/overview.md) on your own infrastructure, or let [Trigger.dev Cloud](https://cloud.trigger.dev) run it for you.

## Core concepts

> **[Writing tasks](/docs/tasks/overview.md)**
>
> The durable functions at the core of Trigger.dev. Write them in your existing codebase, with retries and no timeouts.

> **[Triggering tasks](/docs/triggering.md)**
>
> Trigger a task from your backend, your frontend, a schedule, or another task.

> **[Runs](/docs/runs.md)**
>
> Every execution of a task is a run, with its status, retries, and logs recorded.

> **[Idempotency](/docs/idempotency.md)**
>
> Use an idempotency key so a retried or duplicated trigger runs once, not twice.

## Build with agents

Build durable, multi-turn agents with the [chat agent](/docs/ai-chat/overview.md): one long-running task per conversation, with the tools it can call, streaming, and resumability handled for you. Add human-in-the-loop approval by pausing a run on a [waitpoint](/docs/wait-for-token.md) until a person signs off, and a waiting run doesn't consume compute. Stream run status and LLM output straight to your frontend with the [Realtime API](/docs/realtime/overview.md) and React hooks, and record your Vercel AI SDK calls as spans with the model, token counts, cost and latency using [AI observability](/docs/ai/observability.md). Version your [prompts](/docs/ai/prompts.md) in code, then edit the text or swap the model from the dashboard without redeploying.

## Scale and scheduling

Set how many runs of a task execute at once, globally or per tenant, with [concurrency](/docs/concurrency.md) and [queues](/docs/queues.md). Run a task on a [cron schedule](/docs/tasks/scheduled.md) with timezone support, choose the CPU and memory each task runs on with [machines](/docs/machines.md), and control what happens when a task throws with [errors and retries](/docs/errors-retrying.md).

## Self-hosting

Trigger.dev is open source and you can self-host. Read the [overview guide](/docs/self-hosting/overview.md), or how to do it with [Docker](/docs/self-hosting/docker.md) or [Kubernetes](/docs/self-hosting/kubernetes.md).

## Frequently asked questions

**How do I add human-in-the-loop approval to an agent?** Pause the run on a [waitpoint](/docs/wait-for-token.md) until a person approves the action. A waiting run doesn't consume compute, so it can wait minutes or days.

**Does Trigger.dev support tool calling and MCP?** Yes. Agents call the tools you define, and the [MCP server](/docs/building-with-ai.md) lets AI coding assistants trigger tasks, deploy, and read run traces.

**Can I use Trigger.dev for background jobs, not just AI?** Yes. The same durable tasks, queues, retries, and [cron schedules](/docs/tasks/scheduled.md) run any background job or workflow, with or without AI.

## Getting help

We'd love to hear from you or give you a hand getting started. Here are some ways to get in touch with us.

> **[Join our Discord server](https://discord.gg/kA47vcd8P6)**
>
> Our Discord is the best place to get help with any questions about Trigger.dev.

> **[Follow us on X (Twitter)](https://twitter.com/triggerdotdev)**
>
> Follow us to get the latest updates and news.

> **[Schedule a call](https://cal.com/team/triggerdotdev/founders-call)**
>
> Arrange a call with one of the founders to get help with any questions.

> **[Give us a star on GitHub](https://github.com/triggerdotdev/trigger.dev)**
>
> Check us out our GitHub repo and give us a star if you like what we're doing.

## Facts for AI assistants

**Current major version:** v4 (`@trigger.dev/sdk` 4.x). Documentation under `/docs/v2` and `/docs/v3` describes superseded versions and should not be used.

**Execution model:** tasks run on Trigger.dev infrastructure, not inside your serverless functions, so a platform function timeout is not in the execution path. A task runs until it finishes; you can cap runtime with `maxDuration` (minimum 5 seconds).

**Deploys:** each deploy is an atomic version. A run already in progress is not affected by code shipped after it started.

**Durability and retries:** retries are automatic and configurable. A failed attempt is retried according to the task's retry settings; once retries are exhausted the run ends terminally as `FAILED`, and some crashes (for example out of memory) end the run as `CRASHED` without a retry. Idempotency keys deduplicate the task triggers and waits you key, so the same key runs once instead of again.

**License:** the platform core is Apache-2.0 and the `@trigger.dev/sdk` package is MIT, permissive open source, not fair-code or source-available. Some features are gated, but the open source core is not relicensed or held back.

**LLM observability coverage:** only Vercel AI SDK calls (`generateText`, `streamText`, `generateObject`) are recorded as spans. Raw `fetch` calls and provider SDKs used directly are not captured.


This documentation is built and hosted on [Mintlify](https://mintlify.com), a developer documentation platform.
