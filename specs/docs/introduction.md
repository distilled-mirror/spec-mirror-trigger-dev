> ## Documentation Index
> Fetch the complete documentation index at: https://trigger.dev/docs/llms.txt
> Use this file to discover all available pages before exploring further.

# Welcome to the Trigger.dev docs

> Find all the resources and guides you need to get started

<CardGroup cols={2}>
  <Card title="Quick start" img="https://mintcdn.com/trigger/uys6iMwf9B_ojh8r/images/intro-quickstart.jpg?fit=max&auto=format&n=uys6iMwf9B_ojh8r&q=85&s=3daa6c1f067453c49af4221cb7dae812" href="/docs/quick-start" width="480" height="280" data-path="images/intro-quickstart.jpg">
    Get started with Trigger.dev and run your first task in 3 minutes
  </Card>

  <Card title="Guides, frameworks & examples" img="https://mintcdn.com/trigger/uys6iMwf9B_ojh8r/images/intro-examples.jpg?fit=max&auto=format&n=uys6iMwf9B_ojh8r&q=85&s=a0d04795e0949c204f31dba612d3f351" href="/docs/guides/introduction#example-tasks" width="480" height="280" data-path="images/intro-examples.jpg">
    Browse our wide range of guides, frameworks and example projects
  </Card>

  <Card title="Building with AI" img="https://mintcdn.com/trigger/rLzvmO6Cb9crBewG/images/intro-ai.jpg?fit=max&auto=format&n=rLzvmO6Cb9crBewG&q=85&s=cb80c3aa62f79162d8f96cce6479a844" href="/docs/building-with-ai" width="480" height="280" data-path="images/intro-ai.jpg">
    Learn how to build Trigger.dev projects using AI coding assistants
  </Card>

  <Card title="Video walkthrough" img="https://mintcdn.com/trigger/5SxX7bFjJKRsidSL/images/intro-video.jpg?fit=max&auto=format&n=5SxX7bFjJKRsidSL&q=85&s=3a34fcac5370ad06e3c5d317719a8acc" href="/docs/video-walkthrough" width="480" height="280" data-path="images/intro-video.jpg">
    Watch an end-to-end demo of Trigger.dev in 10 minutes
  </Card>
</CardGroup>

## What is Trigger.dev?

Trigger.dev is an open source background jobs framework that lets you write reliable workflows in plain async code. Run long-running AI tasks, handle complex background jobs, and build AI agents with built-in queuing, automatic retries, and real-time monitoring. No timeouts, elastic scaling, and zero infrastructure management required.

We provide everything you need to build and manage background tasks: a CLI and SDK for writing tasks in your existing codebase, support for both [regular](/docs/tasks/overview) and [scheduled](/docs/tasks/scheduled) tasks, full observability through our dashboard, and a [Realtime API](/docs/realtime) with [React hooks](/docs/realtime/react-hooks#realtime-hooks) for showing task status in your frontend. You can use [Trigger.dev Cloud](https://cloud.trigger.dev) or [self-host](/docs/self-hosting/overview) on your own infrastructure.

## Learn the concepts

<CardGroup cols={2}>
  <Card title="Writing tasks" icon="wand-magic-sparkles" href="/docs/tasks/overview" color="#3B82F6">
    Tasks are the core of Trigger.dev. Learn what they are and how to write them.
  </Card>

  <Card title="Triggering tasks" icon="bullseye-pointer" href="/docs/triggering" color="#fbbf24">
    Learn how to trigger tasks from your codebase.
  </Card>

  <Card title="Runs" icon="person-running" href="/docs/runs" color="#EA189E">
    Runs are the instances of tasks that are executed. Learn how they work.
  </Card>

  <Card title="API keys" icon="key" href="/docs/apikeys" color="#EAEA08">
    API keys are used to authenticate requests to the Trigger.dev API. Learn how to create and use
    them.
  </Card>
</CardGroup>

## Explore by feature

<CardGroup>
  <Card title="Scheduled tasks (cron)" icon="clock" href="/docs/tasks/scheduled" color="#EAEA08">
    Scheduled tasks are a type of task that is scheduled to run at a specific time.
  </Card>

  <Card title="Realtime API" icon="loader" href="/docs/realtime" color="#22C55E">
    The Realtime API allows you to trigger tasks and get the status of runs.
  </Card>

  <Card title="React hooks" icon="react" href="/docs/realtime/react-hooks" color="#3B82F6">
    React hooks are a way to show task status in your frontend.
  </Card>

  <Card title="Waits" icon="calendar-clock" href="/docs/wait" color="#F59E0B">
    Waits are a way to wait for a task to finish before continuing.
  </Card>

  <Card title="Errors and retries" icon="message-exclamation" href="/docs/errors-retrying" color="#F43F5E">
    Learn how to handle errors and retries.
  </Card>

  <Card title="Concurrency & Queues" icon="line-height" href="/docs/queue-concurrency" color="#D946EF">
    Configure what you want to happen when there is more than one run at a time.
  </Card>

  <Card title="Wait for token (human-in-the-loop)" icon="hand" href="/docs/wait-for-token" color="#EAEA08">
    Pause runs until a token is completed via an approval workflow.
  </Card>

  <Card title="Build extensions" icon="gear" href="/docs/config/extensions/overview" color="#22C55E">
    Customize the build process or the resulting bundle and container image.
  </Card>
</CardGroup>

## Explore by build extension

| Extension             | What it does                                                 | Docs                                                                   |
| :-------------------- | :----------------------------------------------------------- | :--------------------------------------------------------------------- |
| prismaExtension       | Use Prisma with Trigger.dev                                  | [prismaExtension docs](/docs/config/extensions/prismaExtension)             |
| pythonExtension       | Execute Python scripts in Trigger.dev                        | [pythonExtension docs](/docs/config/extensions/pythonExtension)             |
| playwright            | Use Playwright with Trigger.dev                              | [playwright extension docs](/docs/config/extensions/playwright)             |
| puppeteer             | Use Puppeteer with Trigger.dev                               | [puppeteer extension docs](/docs/config/extensions/puppeteer)               |
| lightpanda            | Use Lightpanda with Trigger.dev                              | [lightpanda extension docs](/docs/config/extensions/lightpanda)             |
| ffmpeg                | Use FFmpeg with Trigger.dev                                  | [ffmpeg extension docs](/docs/config/extensions/ffmpeg)                     |
| aptGet                | Install system packages with aptGet                          | [aptGet extension docs](/docs/config/extensions/aptGet)                     |
| additionalFiles       | Copy additional files to the build directory                 | [additionalFiles docs](/docs/config/extensions/additionalFiles)             |
| additionalPackages    | Include additional packages in the build                     | [additionalPackages docs](/docs/config/extensions/additionalPackages)       |
| syncEnvVars           | Automatically sync environment variables to Trigger.dev      | [syncEnvVars docs](/docs/config/extensions/syncEnvVars)                     |
| esbuildPlugin         | Add existing or custom esbuild plugins to your build process | [esbuildPlugin docs](/docs/config/extensions/esbuildPlugin)                 |
| emitDecoratorMetadata | Support for the emitDecoratorMetadata TypeScript compiler    | [emitDecoratorMetadata docs](/docs/config/extensions/emitDecoratorMetadata) |
| audioWaveform         | Support for Audio Waveform in your project                   | [audioWaveform docs](/docs/config/extensions/audioWaveform)                 |

## Explore by example

<CardGroup cols={3}>
  <Card title="FFmpeg" img="https://mintcdn.com/trigger/uys6iMwf9B_ojh8r/images/intro-ffmpeg.jpg?fit=max&auto=format&n=uys6iMwf9B_ojh8r&q=85&s=308ca975004d564b951b5247fa42e1ba" href="/docs/guides/examples/ffmpeg-video-processing" width="300" height="160" data-path="images/intro-ffmpeg.jpg" />

  <Card title="Fal.ai" img="https://mintcdn.com/trigger/uys6iMwf9B_ojh8r/images/intro-fal.jpg?fit=max&auto=format&n=uys6iMwf9B_ojh8r&q=85&s=553e3f821fb8ee2776783e992e69063e" href="/docs/guides/examples/fal-ai-image-to-cartoon" width="300" height="160" data-path="images/intro-fal.jpg" />

  <Card title="Puppeteer" img="https://mintcdn.com/trigger/uys6iMwf9B_ojh8r/images/intro-puppeteer.jpg?fit=max&auto=format&n=uys6iMwf9B_ojh8r&q=85&s=d87baa6ed5eb42a9f44c3f192675353f" href="/docs/guides/examples/puppeteer" width="300" height="160" data-path="images/intro-puppeteer.jpg" />

  <Card title="LibreOffice" img="https://mintcdn.com/trigger/uys6iMwf9B_ojh8r/images/intro-libreoffice.jpg?fit=max&auto=format&n=uys6iMwf9B_ojh8r&q=85&s=ef98f3b2a4289ded93b40f454a570ff8" href="/docs/guides/examples/libreoffice-pdf-conversion" width="300" height="160" data-path="images/intro-libreoffice.jpg" />

  <Card title="OpenAI" img="https://mintcdn.com/trigger/uys6iMwf9B_ojh8r/images/intro-openai.jpg?fit=max&auto=format&n=uys6iMwf9B_ojh8r&q=85&s=bb55c727721a1d192f05bfbd4b2aedd0" href="/docs/guides/examples/open-ai-with-retrying" width="300" height="160" data-path="images/intro-openai.jpg" />

  <Card title="Browserbase" img="https://mintcdn.com/trigger/uys6iMwf9B_ojh8r/images/intro-browserbase.jpg?fit=max&auto=format&n=uys6iMwf9B_ojh8r&q=85&s=352fb95a185e61f6eb76b829465f5760" href="/docs/guides/examples/scrape-hacker-news" width="300" height="160" data-path="images/intro-browserbase.jpg" />

  <Card title="Sentry" img="https://mintcdn.com/trigger/5SxX7bFjJKRsidSL/images/intro-sentry.jpg?fit=max&auto=format&n=5SxX7bFjJKRsidSL&q=85&s=984402dfeeff094b78af3f511ae110d6" href="/docs/guides/examples/sentry-error-tracking" width="300" height="160" data-path="images/intro-sentry.jpg" />

  <Card title="Resend" img="https://mintcdn.com/trigger/uys6iMwf9B_ojh8r/images/intro-resend.jpg?fit=max&auto=format&n=uys6iMwf9B_ojh8r&q=85&s=1132b85155953b871bcc310e2d0791ca" href="/docs/guides/examples/resend-email-sequence" width="300" height="160" data-path="images/intro-resend.jpg" />

  <Card title="Vercel AI SDK" img="https://mintcdn.com/trigger/5SxX7bFjJKRsidSL/images/intro-vercel.jpg?fit=max&auto=format&n=5SxX7bFjJKRsidSL&q=85&s=9509bd7265563f221aa2c883a6636604" href="/docs/guides/examples/vercel-ai-sdk" width="300" height="160" data-path="images/intro-vercel.jpg" />

  <Card title="Sharp" img="https://mintcdn.com/trigger/5SxX7bFjJKRsidSL/images/intro-sharp.jpg?fit=max&auto=format&n=5SxX7bFjJKRsidSL&q=85&s=dc7f8fee7e41659bc26c3f82465bcad9" href="/docs/guides/examples/sharp-image-processing" width="300" height="160" data-path="images/intro-sharp.jpg" />

  <Card title="Deepgram" img="https://mintcdn.com/trigger/uys6iMwf9B_ojh8r/images/intro-deepgram.jpg?fit=max&auto=format&n=uys6iMwf9B_ojh8r&q=85&s=feb9e540b0c7f9164afe5f490d1e7f15" href="/docs/guides/examples/deepgram-transcribe-audio" width="300" height="160" data-path="images/intro-deepgram.jpg" />

  <Card title="Supabase" img="https://mintcdn.com/trigger/5SxX7bFjJKRsidSL/images/intro-supabase.jpg?fit=max&auto=format&n=5SxX7bFjJKRsidSL&q=85&s=e12aee521d12d2b5002e9ffe63fd1c43" href="/docs/guides/examples/supabase-database-operations" width="300" height="160" data-path="images/intro-supabase.jpg" />

  <Card title="DALL•E" img="https://mintcdn.com/trigger/uys6iMwf9B_ojh8r/images/intro-openai.jpg?fit=max&auto=format&n=uys6iMwf9B_ojh8r&q=85&s=bb55c727721a1d192f05bfbd4b2aedd0" href="/docs/guides/examples/dall-e3-generate-image" width="300" height="160" data-path="images/intro-openai.jpg" />

  <Card title="Firecrawl" img="https://mintcdn.com/trigger/uys6iMwf9B_ojh8r/images/intro-firecrawl.jpg?fit=max&auto=format&n=uys6iMwf9B_ojh8r&q=85&s=c992f70dfa2e7324a5a6c23fdfb5f1ce" href="/docs/guides/examples/firecrawl-url-crawl" width="300" height="160" data-path="images/intro-firecrawl.jpg" />

  <Card title="Lightpanda" img="https://mintcdn.com/trigger/uys6iMwf9B_ojh8r/images/intro-lightpanda.jpg?fit=max&auto=format&n=uys6iMwf9B_ojh8r&q=85&s=f0d242338bf995c2872da2aac5cefd7b" href="/docs/guides/examples/lightpanda" width="300" height="160" data-path="images/intro-lightpanda.jpg" />
</CardGroup>

## Getting help

We'd love to hear from you or give you a hand getting started. Here are some ways to get in touch with us.

<CardGroup>
  <Card title="Join our Discord server" icon="discord" href="https://discord.gg/kA47vcd8P6" color="#5865F2">
    Our Discord is the best place to get help with any questions about Trigger.dev.
  </Card>

  <Card
    title="Follow us on X (Twitter)"
    icon={
  <svg xmlns="http://www.w3.org/2000/svg" height="20" viewBox="0 0 512 512">
    <path d="M389.2 48h70.6L305.6 224.2 487 464H345L233.7 318.6 106.5 464H35.8L200.7 275.5 26.8 48H172.4L272.9 180.9 389.2 48zM364.4 421.8h39.1L151.1 88h-42L364.4 421.8z" />
  </svg>
}
    href="https://twitter.com/triggerdotdev"
    color="#1DA1F2"
  >
    Follow us to get the latest updates and news.
  </Card>

  <Card title="Schedule a call" icon="phone" iconType="solid" color="#22C55E" href="https://cal.com/team/triggerdotdev/founders-call">
    Arrange a call with one of the founders to get help with any questions.
  </Card>

  <Card title="Give us a star on GitHub" icon="star" iconType="solid" href="https://github.com/triggerdotdev/trigger.dev" color="#fbbf24">
    Check us out our GitHub repo and give us a star if you like what we're doing.
  </Card>
</CardGroup>
