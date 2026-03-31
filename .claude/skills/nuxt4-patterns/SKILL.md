# Nuxt 4 Patterns Skill

Modern patterns for Nuxt 4 development.

## Key Changes from Nuxt 3

- New directory structure (`app/` folder)
- Improved TypeScript support
- Native Vue 3.4+ features
- Enhanced dev server

## Directory Structure

```
app/
├── components/
├── composables/
├── layouts/
├── pages/
├── plugins/
└── app.vue
server/
├── api/
├── middleware/
└── plugins/
```

## Data Fetching

```typescript
// Preferred: useFetch with key
const { data } = await useFetch('/api/data', {
  key: 'unique-key',
  transform: (data) => data.items
})

// Server-only fetch
const data = await $fetch('/api/data', {
  server: true
})
```

## State Management

```typescript
// Composable pattern
export const useCounter = () => {
  const count = useState('counter', () => 0)
  const increment = () => count.value++
  return { count, increment }
}
```

## Performance Tips

- Use `<NuxtImg>` for optimized images
- Lazy load components with `<LazyComponent>`
- Leverage `useAsyncData` for parallel fetching
- Use `shallowRef` for large objects
