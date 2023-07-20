---
title: Redirect vs Rewrites
date: 2023-07-19 13:30:00 +0100
categories: [Coding, Next.js]
tags: [nextjs] # TAG names should always be lowercase
author: <author_id>
---

```jsx
async redirects() {
    return [
      {
        source: '/contact',
        destination: '/form',
        permanent: false,
      },
    ];
  },
```

if user go to `/contact`, it automatically rediret to `/form` page

```jsx
async redirects() {
  return [
    {
      source: '/old-blog/:path*',
      destination: '/new-blog/:path*',
      permanent: false,
    },
  ];
},
```

it directly leads to `new-blog/sameId`

```jsx
async rewrites() {
    return [
      {
        source: '/api/movies',
        destination: `https://api.themoviedb.org/3/movie/popular?api_key=${API_KEY}`,
      },
    ];
  },
```

next.js can mask our api key!
