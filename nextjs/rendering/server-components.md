# Server Components

React Server Components allow you to write UI that can be rendered and optionally cached on the server. In Next.js, the rendering work is further split by route segments to enable streaming and partial rendering, and there are three different server rendering strategies:

By default, any component in Next.js App Router (`/app`) is a Server Component.

- **Static Rendering (Default)**

- **Dynamic Rendering**

- **Streaming**


## What are Server Components?
- ✅ Rendered on the server
- ✅ Direct database/API access
- ✅ SEO-friendly – Content is already rendered when sent to the client.
- ✅ Can include client components – Use `use client` when needed.


## Static Rendering (Default)

With Static Rendering, routes are rendered at build time.

Static rendering is useful when a route has data that is not personalized to the user and can be known at build time, such as a static blog post or a product page.

## Dynamic Rendering

With Dynamic Rendering, routes are rendered for each user at request time.

Dynamic rendering is useful when a route has data that is personalized to the user or has information that can only be known at request time, such as cookies or the URL's search params.

Using any of these APIs signals the developer's intention and will opt the whole route into dynamic rendering at the request time. These APIs include:

- `cookies`
- `headers`
- `connection`
- `draftMode`
- `searchParams` prop
- `unstable_noStore`