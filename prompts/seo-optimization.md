**Prompt: Make this React/SPA application SEO-friendly**

Analyze my current application and implement SEO optimizations. Here's what I need:

## 1. SSR/SSG Setup (if not already implemented)
- If this is a plain React app, provide migration steps to Next.js with SSR/SSG
- If already using Next.js, ensure pages are using `getStaticProps` or `getServerSideProps` appropriately
- If migration isn't feasible, implement react-snap or similar pre-rendering solution

## 2. Meta Tags & Head Management
**For React 19+:** Use native `<title>`, `<meta>`, and `<link>` tags directly in components
**For Next.js:** Use the `<Head>` component from `next/head` or Metadata API (App Router)
**For older React versions:** Use `react-helmet-async`

Add dynamic meta tags for EVERY route/page:
- `<title>` (50-60 characters, unique per page)
- Meta description (150-160 characters, compelling and unique)
- Open Graph tags (og:title, og:description, og:image, og:url, og:type)
- Twitter Card tags (twitter:card, twitter:title, twitter:description, twitter:image)
- Canonical URLs to prevent duplicate content issues

Create a reusable SEO component that accepts props for each page. Example structure:
```jsx
// React 19+ native approach
function PageComponent() {
  return (
    <>
      <title>Page Title</title>
      <meta name="description" content="Description here" />
      <meta property="og:title" content="Page Title" />
      {/* ... rest of content */}
    </>
  );
}
```

## 3. Semantic HTML & Accessibility
- Replace generic `<div>` elements with semantic HTML: `<header>`, `<nav>`, `<main>`, `<article>`, `<section>`, `<footer>`
- Ensure proper heading hierarchy (h1 → h2 → h3, only one h1 per page)
- Add descriptive `alt` attributes to all images
- Ensure all interactive elements are keyboard accessible
- Add ARIA labels where appropriate

## 4. Performance Optimizations
- Implement code splitting and lazy loading for routes and heavy components (React.lazy, Suspense)
- Optimize images: use Next.js `<Image>` component or implement lazy loading with proper sizing
- Add loading states and skeleton screens
- Minimize JavaScript bundle size (check for unused dependencies)
- Implement proper caching headers in `vercel.json` or `next.config.js`

## 5. Structured Data (Schema.org)
- Add JSON-LD structured data for:
  - WebSite schema
  - Organization/Person schema (about me/project)
  - Any specific schemas relevant to the project (Article, SoftwareApplication, etc.)
- Place structured data in the `<head>` or via `<script type="application/ld+json">` tags

## 6. Sitemap & Robots.txt
- Generate `sitemap.xml` with all public routes
- Create `robots.txt` that allows crawling of public pages
- For Next.js, use `next-sitemap` package or create custom API route
- Ensure sitemap is submitted to Google Search Console

## 7. URL Structure & Routing
- Ensure URLs are descriptive and include relevant keywords (e.g., `/projects/seo-tool` not `/project/1`)
- Implement proper 404 page
- Add breadcrumb navigation if applicable
- Ensure no broken links

## 8. Social Sharing Preview
- Create Open Graph images (1200x630px) for main pages
- Test preview appearance using Facebook Debugger and Twitter Card Validator
- Store OG images in `/public` folder with descriptive names

## 9. Analytics & Monitoring Setup
- Add Google Analytics 4 or alternative (Plausible, Umami)
- Implement proper event tracking for key user actions
- Add Google Search Console verification meta tag

## 10. Technical Checklist
- Ensure HTTPS is enforced (Vercel does this by default)
- Add `viewport` meta tag for mobile responsiveness
- Implement proper error boundaries
- Add loading indicators for async content
- Ensure the site works with JavaScript disabled (at least shows basic content)

## Output Format:
1. List all files that need to be modified with specific changes
2. Provide complete code for new components (SEO component, structured data, etc.)
3. Include configuration file updates (`next.config.js`, `vercel.json`, `package.json`)
4. Give step-by-step migration instructions if framework changes are needed
5. Provide a testing checklist to verify SEO improvements
