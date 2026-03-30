# Next.js Turbopack Patterns

## Purpose
Best practices for Next.js with Turbopack bundler.

## Enable Turbopack

```bash
# Development (recommended)
next dev --turbo

# Or in package.json
"scripts": {
  "dev": "next dev --turbo"
}
```

## Key Patterns

### App Router Structure
```
app/
├── layout.tsx        # Root layout
├── page.tsx          # Home page
├── loading.tsx       # Loading UI
├── error.tsx         # Error boundary
├── not-found.tsx     # 404 page
└── (routes)/
    └── [slug]/
        └── page.tsx
```

### Server Components (Default)
```tsx
// app/posts/page.tsx - Server Component by default
async function PostsPage() {
  const posts = await db.posts.findMany()
  return <PostList posts={posts} />
}
```

### Client Components
```tsx
'use client'

import { useState } from 'react'

export function Counter() {
  const [count, setCount] = useState(0)
  return <button onClick={() => setCount(c => c + 1)}>{count}</button>
}
```

### Server Actions
```tsx
// app/actions.ts
'use server'

export async function createPost(formData: FormData) {
  const title = formData.get('title')
  await db.posts.create({ data: { title } })
  revalidatePath('/posts')
}
```

### Data Fetching
```tsx
// Parallel fetching
async function Page() {
  const [posts, users] = await Promise.all([
    fetchPosts(),
    fetchUsers()
  ])
}

// With caching
const getPosts = cache(async () => {
  return await db.posts.findMany()
})
```

## Performance Tips

1. **Use Server Components** - Reduce client bundle
2. **Streaming** - Use `loading.tsx` and Suspense
3. **Image Optimization** - Use `next/image`
4. **Font Optimization** - Use `next/font`
5. **Static Generation** - Use `generateStaticParams`

## Common Issues

```tsx
// ❌ Using hooks in Server Component
export default function Page() {
  const [state, setState] = useState() // Error!
}

// ✅ Mark as Client Component
'use client'
export default function Page() {
  const [state, setState] = useState() // OK
}
```
