# Incremental Static Regeneration (ISR)

- Update static content without rebuilding the entire site
- Reduce server load by serving prerendered, static pages for most requests
- Ensure proper `cache-control` headers are automatically added to pages
- Handle large amounts of content pages without long `next build` times

## Time-based revalidation
exporting a variable called `revalidate` and set it equal to the number of seconds of when you want to revalidate it.

```js
export const revalidate = 3600 // invalidate every hour
```