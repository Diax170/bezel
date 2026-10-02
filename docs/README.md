# Documentation publishing

`guide.md` is the source for https://hitanshu.xyz/bezel/docs. Edit it here with the related code changes.

The portfolio builds the page with Astro. During each build, it resolves Bezel's `main` branch to a commit and downloads `docs/guide.md` from `raw.githubusercontent.com` at that commit. Markdown becomes static HTML with syntax highlighting and section navigation. Visitors do not need a GitHub request to read the page.

Documentation updates appear after the next portfolio deployment. Redeploy the portfolio when changes to this guide should go live. A failed GitHub request fails the build, so an existing deployment is not replaced with an empty docs page.

For a local portfolio preview before publishing the guide:

```sh
BEZEL_DOCS_PATH=/absolute/path/to/bezel/docs/guide.md npm run dev
```

Use the same environment variable with `npm run build` to validate unpublished content. Production builds should leave it unset. `BEZEL_DOCS_REF` can select a published branch, tag, or commit; its default is `main`.

Publish `docs/guide.md` to Bezel first, deploy the portfolio next, then publish the shortened README. The GitHub copy remains available for offline reading and contribution review.
