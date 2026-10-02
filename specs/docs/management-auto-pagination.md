> ## Documentation Index
> Fetch the complete documentation index at: https://trigger.dev/docs/llms.txt
> Use this file to discover all available pages before exploring further.

# Auto-pagination

> Using auto-pagination with the Trigger.dev management API

All list endpoints in the management API support auto-pagination.
You can use `for await … of` syntax to iterate through items across all pages:

```ts theme={"theme":"css-variables"}
import { runs } from "@trigger.dev/sdk";

async function fetchAllRuns() {
  const allRuns = [];

  for await (const run of runs.list({ limit: 10 })) {
    allRuns.push(run);
  }

  return allRuns;
}
```

You can also use helpers on the return value from any `list` method to get the next/previous page of results:

```ts theme={"theme":"css-variables"}
import { runs } from "@trigger.dev/sdk";

async function main() {
  let page = await runs.list({ limit: 10 });

  for (const run of page.data) {
    console.log(run);
  }

  while (page.hasNextPage()) {
    page = await page.getNextPage();
    // ... do something with the next page
  }
}
```


This documentation is built and hosted on [Mintlify](https://mintlify.com), a developer documentation platform.
