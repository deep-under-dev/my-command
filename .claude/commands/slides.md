# Slides - HTML Presentation Builder

Build animation-rich, zero-dependency HTML slide decks.

## Usage

```
/slides "topic or outline"
```

## Output

- Single HTML file with embedded CSS/JS
- Works offline, no dependencies
- Viewport-fit: 1920x1080 (16:9)
- Keyboard navigation (arrows, space)

## Structure

```html
<!DOCTYPE html>
<html>
<head>
  <style>/* All styles inline */</style>
</head>
<body>
  <div class="slide" id="slide-1">...</div>
  <div class="slide" id="slide-2">...</div>
  <script>/* Navigation logic */</script>
</body>
</html>
```

## Design Principles

1. **One idea per slide** - Keep it focused
2. **Large text** - Minimum 32px for body, 48px+ for headers
3. **High contrast** - Dark on light or light on dark
4. **Animations** - CSS transitions, subtle and purposeful
5. **Images** - Use placeholder boxes with descriptions if needed

## Workflow

1. Understand the topic/outline
2. Create slide structure (title, content, conclusion)
3. Add visual hierarchy and transitions
4. Test navigation works
5. Output single HTML file

## Example Themes

- **Minimal**: White bg, black text, accent color
- **Dark**: Dark bg (#1a1a2e), light text, gradient accents
- **Corporate**: Navy/white, clean lines, subtle shadows

## Tips

- Use CSS Grid/Flexbox for layouts
- Add speaker notes as HTML comments
- Include progress indicator
- Support both click and keyboard nav
