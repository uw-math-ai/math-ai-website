# Math AI Website

Root SvelteKit site for the University of Washington Math AI Lab.

## Development

```sh
npm install
npm run dev
```

## Build

```sh
npm run check
npm run build
```

The production site is written to `build/`. Deploy the contents of `build/` to the static host root. The live `ai.math.uw.edu` domain currently redirects to `https://sites.math.washington.edu/ai/`, so the build is configured for static domain-root hosting rather than a GitHub Pages subpath.

## Events

The event calendar is repo-owned data in `src/lib/data/events.ts`. To add an event, append one object with:

- `title`
- `speaker`
- `date` as `YYYY-MM-DD`
- `startTime` and `endTime` as 24-hour `HH:mm`
- `location`
- `type`
- `sourceUrl`
- optional `abstract`

Use UW Math event pages as the source URL whenever possible.

## Static Redirects

Public quarter URLs such as `spring2026.html` are lightweight redirect shims in `static/` so existing links keep working after the SvelteKit migration.
