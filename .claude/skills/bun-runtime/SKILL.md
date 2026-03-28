# Bun Runtime Patterns

Best practices for Bun runtime development.

## When to Use

- Building with Bun runtime
- Migrating from Node.js to Bun
- Optimizing Bun applications

## Key Patterns

### File I/O
```typescript
// Fast file reading
const file = Bun.file("./data.json");
const data = await file.json();

// Fast file writing
await Bun.write("./output.txt", "content");
```

### HTTP Server
```typescript
Bun.serve({
  port: 3000,
  fetch(req) {
    return new Response("Hello Bun!");
  },
});
```

### SQLite (Built-in)
```typescript
import { Database } from "bun:sqlite";
const db = new Database("mydb.sqlite");
```

### Package Management
```bash
bun install          # Install deps (faster than npm)
bun add package      # Add package
bun run script       # Run script
bun build ./index.ts # Bundle
```

## Performance Tips

1. Use `Bun.file()` over `fs.readFile()`
2. Leverage built-in SQLite for local data
3. Use `bun:test` for fast testing
4. Prefer `Bun.serve()` over Express for simple APIs
