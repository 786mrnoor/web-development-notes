# Client Components

Client Components allow you to write interactive UI that is prerendered on the server and can use client JavaScript to run in the browser.

To use Client Components, you can add the React `"use client"` directive at the top of a file, above your imports.

`"use client"` is used to declare a boundary between a Server and Client Component modules. This means that by defining a `"use client"` in a file, all other modules imported into it, including child components, are considered part of the client bundle.

## How are Client Components Rendered?

- **Full page load**: Next.js will use React's APIs to render a static HTML preview on the server for both Client and Server Components. This means, when the user first visits your application, they will see the content of the page immediately, without having to wait for the client to download, parse, and execute the Client Component JavaScript bundle.

- **Subsequent Navigations**: On subsequent navigations, Client Components are rendered entirely on the client, without the server-rendered HTML.  
This means the Client Component JavaScript bundle is downloaded and parsed. Once the bundle is ready, React will use the RSC Payload to reconcile the Client and Server Component trees, and update the DOM.