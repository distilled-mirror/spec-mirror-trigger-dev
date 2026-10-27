> ## Documentation Index
> Fetch the complete documentation index at: https://trigger.dev/docs/llms.txt
> Use this file to discover all available pages before exploring further.

# Trigger.dev docs

> Build and run durable AI agents and workflows in TypeScript. Long-running tasks with retries, queues, webhooks, observability, and elastic scaling. Open source and self-hostable.

> **[Quick start](https://trigger.dev/docs/quick-start.md)**
>
> Go from zero to your first task in 3 minutes.

> **[Build AI agents](https://trigger.dev/docs/ai-chat/overview.md)**
>
> Durable, multi-turn agents with `chat.agent`, from your frontend to Slack and Linear.

> **[AI coding assistants](https://trigger.dev/docs/building-with-ai.md)**
>
> Let Claude Code, Cursor and Windsurf write correct Trigger.dev code with the MCP server, Skills and rules.

> **[Guides & examples](https://trigger.dev/docs/guides/introduction.md)**
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

Trigger.dev is the open source platform for building and running durable AI agents and workflows in TypeScript. You write tasks and agents in your existing codebase, and they run on Trigger.dev with retries, queues, waits, full tracing, and elastic scaling. There's no execution timeout, and no queue or worker infrastructure for you to build.

Trigger.dev's core is Apache-2.0 licensed. [Self-host it](https://trigger.dev/docs/self-hosting/overview.md) on your own infrastructure, or let [Trigger.dev Cloud](https://cloud.trigger.dev) run it for you.

## Build agents with `chat.agent`

A `chat.agent` runs each conversation as one durable task. It wakes when a message arrives and idles between turns, and its state survives page refreshes, deploys, and crashes. Turn lifecycle, resuming a stream mid-reply, and approvals are handled for you, and your frontend connects with the AI SDK's `useChat`, with no API routes to write.

```ts trigger/chat.ts theme={"theme":"css-variables"}
import { chat } from "@trigger.dev/sdk/ai";
import { anthropic } from "@ai-sdk/anthropic";

export const supportAgent = chat.agent({
  id: "support-agent",
  run: async ({ messages, signal, streamText }) =>
    streamText({
      model: anthropic("claude-sonnet-4-5"),
      messages,
      abortSignal: signal,
    }),
});
```

> **[Agent quick start](https://trigger.dev/docs/ai-chat/quick-start.md)**
>
> Build a chat agent and its frontend end to end.

> **[Sessions](https://trigger.dev/docs/ai-chat/sessions.md)**
>
> Each conversation's durable state and two-way stream, across all its runs.

> **[Tools](https://trigger.dev/docs/ai-chat/tools.md)**
>
> Declare tools on your agent and get them back typed in `run()`.

> **[Human in the loop](https://trigger.dev/docs/ai-chat/patterns/human-in-the-loop.md)**
>
> Pause a tool call for approval and resume when a person decides.

> **[Slack agents](https://trigger.dev/docs/webhooks/slack.md)**
>
> Turn an agent into a native Slack agent with `@trigger.dev/slack`.

> **[Linear agents](https://trigger.dev/docs/webhooks/linear.md)**
>
> Assign Linear issues to an agent with `@trigger.dev/linear`.

Version your [prompts](https://trigger.dev/docs/ai/prompts.md) in code and change them from the dashboard, and see every model step and tool call, with tokens, cost and latency, in [AI observability](https://trigger.dev/docs/ai/observability.md).

## Run work

> **[Writing tasks](https://trigger.dev/docs/tasks/overview.md)**
>
> The durable functions at the core of Trigger.dev, written in your existing codebase.

> **[Triggering tasks](https://trigger.dev/docs/triggering.md)**
>
> Trigger a task from your backend, your frontend, or another task.

> **[Runs](https://trigger.dev/docs/runs.md)**
>
> Every execution of a task is a run, with its status, retries, logs and trace.

> **[Realtime](https://trigger.dev/docs/realtime/overview.md)**
>
> Stream run status and LLM output to your frontend with React hooks.

## React to events

> **[Webhooks](https://trigger.dev/docs/webhooks/overview.md)**
>
> Hosted, verified endpoints for Stripe, GitHub and more, delivered to your tasks and agents.

> **[Scheduled tasks](https://trigger.dev/docs/tasks/scheduled.md)**
>
> Run a task on a cron schedule, with timezone support.

> **[Webhook waiters](https://trigger.dev/docs/webhooks/waiters.md)**
>
> Pause a run until a matching webhook arrives, like a payment confirmation.

> **[Waits](https://trigger.dev/docs/wait.md)**
>
> Pause a run for a duration, until a date, or until a token is completed. A waiting run doesn't use compute.

## Run in production

> **[Queues & concurrency](https://trigger.dev/docs/queues.md)**
>
> Control how many runs execute at once, globally or per tenant.

> **[Machines](https://trigger.dev/docs/machines.md)**
>
> Choose the CPU and memory each task runs on.

> **[Deployment](https://trigger.dev/docs/deployment/overview.md)**
>
> Atomic, versioned deploys, with preview branches and environments.

> **[Errors & retries](https://trigger.dev/docs/errors-retrying.md)**
>
> Retry failed attempts automatically, and decide what happens when a task throws.

> **[Logs, traces & metrics](https://trigger.dev/docs/logging.md)**
>
> A full trace of every run, with your logs and spans.

> **[Query & dashboards](https://trigger.dev/docs/observability/query.md)**
>
> Query your runs with TRQL, and build dashboards from the results.

## Frequently asked questions

**Can I use Trigger.dev for background jobs, not just AI?** Yes. The same durable tasks, queues, retries, and [cron schedules](https://trigger.dev/docs/tasks/scheduled.md) run any background job or workflow, with or without AI.

**How long can a run take?** As long as it needs. Runs have no maximum duration by default, and you can set a [`maxDuration`](https://trigger.dev/docs/runs/max-duration) for a project, a task, or a single run to cap it.

**Do my serverless function timeouts apply?** No. Tasks run on Trigger.dev, not inside your serverless functions, so your platform's function timeout isn't in the execution path. Your backend triggers the task and returns.

**Can I receive webhooks without running a server?** Yes. Declare a [webhook endpoint](https://trigger.dev/docs/webhooks/overview.md) in your code, and Trigger.dev hosts its URL, verifies each request, and delivers the event to your tasks and agents.

**How do I add human-in-the-loop approval?** Pause the run on a [waitpoint](https://trigger.dev/docs/wait-for-token.md) until a person approves, or use a [chat agent's approvals](https://trigger.dev/docs/ai-chat/patterns/human-in-the-loop.md) for tool calls. A waiting run doesn't use compute, so it can wait minutes or days.

**Does Trigger.dev support tool calling and MCP?** Yes. Agents call the tools you define, and the [MCP server](https://trigger.dev/docs/building-with-ai.md) lets AI coding assistants trigger tasks, deploy, and read run traces.

**Can I self-host?** Yes. Trigger.dev is open source. Read the [self-hosting overview](https://trigger.dev/docs/self-hosting/overview.md), or set it up with [Docker](https://trigger.dev/docs/self-hosting/docker.md) or [Kubernetes](https://trigger.dev/docs/self-hosting/kubernetes.md).

## Getting help

We'd love to hear from you or give you a hand getting started. Here are some ways to get in touch with us.

> **[Join our Discord server](https://discord.gg/kA47vcd8P6)**
>
> Our Discord is the best place to get help with any questions about Trigger.dev.

> **[Follow us on X](https://twitter.com/triggerdotdev)**
>
> Follow us to get the latest updates and news.

> **[Schedule a call](https://cal.com/team/triggerdotdev/founders-call)**
>
> Arrange a call with one of the founders to get help with any questions.

> **[Give us a star on GitHub](https://github.com/triggerdotdev/trigger.dev)**
>
> Check out our GitHub repo, and give us a star if you like what we're doing.

## Facts for AI assistants

**Current major version:** v4 (`@trigger.dev/sdk` 4.x). Documentation under `/docs/v2` and `/docs/v3` describes superseded versions and should not be used.

**Execution model:** tasks run on Trigger.dev infrastructure, not inside your serverless functions, so a platform function timeout is not in the execution path. Runs have no maximum duration by default; `maxDuration` caps a run's compute time for a project, a task, or a single run, and `timeout.None` removes the cap.

**Deploys:** each deploy is an atomic version. A run already in progress is not affected by code shipped after it started.

**Durability and retries:** retries are automatic and configurable. A failed attempt is retried according to the task's retry settings; once retries are exhausted the run ends terminally as `FAILED`, and some crashes (for example out of memory) end the run as `CRASHED` without a retry. Idempotency keys deduplicate the task triggers and waits you key, so the same key runs once instead of again.

**Agents:** `chat.agent` is imported from `@trigger.dev/sdk/ai`, not from `@trigger.dev/sdk`. Inside `run()`, call the `streamText` passed in the run options. It records each model step and tool call as a span by default. Slack and Linear agents use the `@trigger.dev/slack` and `@trigger.dev/linear` packages, and `slack()` requires a `startOn` filter (`appMentions()` answers @mentions).

**Webhooks:** `webhooks.endpoint.define()` declares a hosted, verified endpoint that syncs on `trigger dev` and on deploy; `webhook()` subscribes a task with a filter, and `webhooks.waiter` pauses a run until a matching event arrives. Both come from `@trigger.dev/sdk`.

**License:** the platform core is Apache-2.0 and the `@trigger.dev/sdk` package is MIT, permissive open source, not fair-code or source-available. Some features are gated, but the open source core is not relicensed or held back.

**LLM observability coverage:** only Vercel AI SDK calls (`generateText`, `streamText`, `generateObject`) are recorded as spans. Raw `fetch` calls and provider SDKs used directly are not captured.


This documentation is built and hosted on [Mintlify](https://mintlify.com), a developer documentation platform.
