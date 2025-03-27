### **Next.js App Router (New Folder Structure)**  
The **App Router** in Next.js 13+ (with the `/app` directory) introduces a **server-first architecture** using React Server Components (RSC) and new routing features.  

---

## **📂 Folder Structure**
```
my-nextjs-app/
│── public/             # Static assets (images, fonts, etc.)
│── src/                # Source code (optional, better organization)
│   ├── app/            # App Router (Replaces "pages")
│   │   ├── layout.tsx  # Root layout (wraps all pages)
│   │   ├── page.tsx    # Home page (default route)
│   │   ├── about/      # Nested route → "/about"
│   │   │   ├── page.tsx 
│   │   ├── blog/       # Dynamic routes
│   │   │   ├── page.tsx  
│   │   │   ├── [id]/   # Dynamic segment → "/blog/:id"
│   │   │   │   ├── page.tsx  
│   │   ├── api/        # API routes (new approach)
│   │   │   ├── route.ts # API endpoint (Replaces "pages/api")
│   │   ├── dashboard/  # Protected route (auth middleware)
│   │   │   ├── layout.tsx  # Nested layout for dashboard
│   │   │   ├── page.tsx
│   ├── components/     # Reusable UI components (buttons, modals)
│   ├── lib/            # Utility functions, API clients
│   ├── styles/         # Global styles (CSS, Tailwind)
│   ├── middleware.ts   # Middleware (Auth, redirects)
│── .env.local          # Environment variables
│── next.config.js      # Next.js configuration
│── package.json        # Dependencies and scripts
│── tsconfig.json       # TypeScript configuration
│── README.md           # Documentation
```

---

## **📌 Key Features of App Router**
### ✅ **1. `/app` Directory (Replaces `/pages`)**  
- Each folder inside `/app` is a **route**.  
- `page.tsx` inside a folder defines the route’s page component.  
- `layout.tsx` wraps child routes inside the same folder.  

**Example:**  
- `/app/about/page.tsx` → Renders **/about**  
- `/app/blog/[id]/page.tsx` → Renders **/blog/:id**  

---

### ✅ **2. `layout.tsx` (Shared Layouts)**
Each route can have its **own layout** to avoid reloading shared components.

**Example:**  
`app/layout.tsx` → Root layout applied to all pages  
```tsx
export default function RootLayout({ children }) {
  return (
    <html lang="en">
      <body>
        <Navbar />
        {children}
        <Footer />
      </body>
    </html>
  );
}
```

---

### ✅ **3. Dynamic Routes (`[param]`)**
- Wrap folder names in square brackets `[id]` for dynamic routing.  
- Example: `app/blog/[id]/page.tsx` → `blog/:id`.  

```tsx
export default function BlogPost({ params }: { params: { id: string } }) {
  return <h1>Blog Post ID: {params.id}</h1>;
}
```

---

### ✅ **4. API Routes (`route.ts`)**
API routes are now inside `/app/api/*`.  
```tsx
// app/api/hello/route.ts
import { NextResponse } from "next/server";

export async function GET() {
  return NextResponse.json({ message: "Hello API!" });
}
```
- Access it at `/api/hello`.  

---

### ✅ **5. Middleware (`middleware.ts`)**
Middleware runs **before the request is processed** (e.g., auth checks).  

```tsx
import { NextResponse } from "next/server";

export function middleware(request) {
  const isAuthenticated = request.cookies.get("token");
  if (!isAuthenticated) {
    return NextResponse.redirect("/login");
  }
  return NextResponse.next();
}
```

---

### ✅ **6. `loading.tsx` (Automatic Loading States)**
Next.js **App Router** supports `loading.tsx` for **suspense-based loading UI**.  

```tsx
export default function Loading() {
  return <p>Loading...</p>;
}
```
- Placing `loading.tsx` inside a route **shows a loading UI** until the page loads.  

---

## **🚀 Best Practices for App Router**
✅ **Use `/app` for routing instead of `/pages`.**  
✅ **Use `layout.tsx` for shared layouts (navbar, footer).**  
✅ **Use `loading.tsx` for smooth loading experiences.**  
✅ **Use `route.ts` inside `api/` for server-side API routes.**  
✅ **Fetch data using `fetch()` inside Server Components (RSC).**  

Would you like a project setup guide or examples for a specific feature? 😊