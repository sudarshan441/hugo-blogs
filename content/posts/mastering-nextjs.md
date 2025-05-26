---
title: "Mastering Next.js: The Complete Guide to React Framework Power"
date: 2025-05-26T15:00:00+05:30
draft: false
tags: ["Next.js", "React", "Fullstack", "Web Development", "SSR", "SSG", "API Routes"]
categories: ["Tech", "Development"]
author: "Sudarshan"
summary: "A full guide to building high-performance applications using Next.js, covering routing, data fetching, API routes, and deployment."
---

# Mastering Next.js: The Complete Guide to React Framework Power

Next.js is a fullstack React framework for building fast, SEO-friendly web applications. It provides hybrid static & server rendering, TypeScript support, smart bundling, and much more.

In this guide, you’ll learn:

- What is Next.js?  
- Pages and File-based Routing  
- Linking Between Pages  
- Static Generation (SSG) and Server-side Rendering (SSR)  
- API Routes  
- Image Optimization  
- Dynamic Routes and Catch-All Routes  
- Deployment with Vercel  

---

## 1. What is Next.js?

Next.js builds on top of React to enable features like SSR, SSG, and more. It's ideal for performance, SEO, and developer experience.

Installation:

```bash
npx create-next-app@latest my-app
cd my-app
npm run dev
```

---

## 2. Pages and File-based Routing

Next.js uses the `pages/` directory for routing.

**`pages/index.js`** becomes `/`  
**`pages/about.js`** becomes `/about`

```jsx
// pages/about.js
export default function About() {
  return <h1>About Page</h1>;
}
```

---

## 3. Linking Between Pages

Use the built-in `Link` component for navigation:

```jsx
import Link from 'next/link';

export default function Home() {
  return (
    <div>
      <h1>Home</h1>
      <Link href="/about">Go to About</Link>
    </div>
  );
}
```

---

## 4. Static Generation (SSG) and Server-side Rendering (SSR)

### Static Generation

```jsx
export async function getStaticProps() {
  return {
    props: {
      message: 'Hello from SSG',
    },
  };
}
```

### Server-side Rendering

```jsx
export async function getServerSideProps() {
  return {
    props: {
      message: 'Hello from SSR',
    },
  };
}
```

---

## 5. API Routes

API routes live in the `pages/api/` folder.

```js
// pages/api/hello.js
export default function handler(req, res) {
  res.status(200).json({ message: 'Hello from API route' });
}
```

---

## 6. Image Optimization

Next.js provides the `Image` component for optimized images.

```jsx
import Image from 'next/image';
import profilePic from '../public/profile.jpg';

export default function Profile() {
  return <Image src={profilePic} alt="Profile" width={200} height={200} />;
}
```

---

## 7. Dynamic Routes and Catch-All Routes

**Dynamic route:** `pages/post/[id].js`  
**Catch-all route:** `pages/post/[...slug].js`

```jsx
// pages/post/[id].js
import { useRouter } from 'next/router';

export default function Post() {
  const router = useRouter();
  const { id } = router.query;

  return <p>Post ID: {id}</p>;
}
```

---

## 8. Deployment with Vercel

Deploy directly using:

```bash
npx vercel
```

Or push to GitHub and import in [vercel.com](https://vercel.com).

---

## Best Practices

- Use `getStaticProps` for content that doesn't change often  
- Use `getServerSideProps` for personalized or frequently updated data  
- Optimize images with the `Image` component  
- Keep API logic inside `pages/api`  
- Use `next/head` to manage metadata for SEO  
- Enable TypeScript for better developer experience  
- Split components into reusable folders  

---

## Conclusion

Next.js simplifies React development by giving you performance, scalability, and fullstack capabilities out of the box.

Use it to build everything from landing pages to full-fledged web apps.

Happy building! 🚀
