# Frontend Slides Skill

Build animation-rich, zero-dependency HTML slide decks.

## Purpose
Create web-native presentations without PowerPoint. Perfect for:
- Tech talks
- Product demos
- Internal presentations
- Portfolio showcases

## Core Principles

### Viewport-Fit Rules
- Design for 16:9 aspect ratio
- Content must fit without scrolling
- Use `vh/vw` units for responsive sizing
- Test at 1920x1080 and 1280x720

### Zero Dependencies
- Pure HTML/CSS/JS
- No external libraries required
- Single HTML file output
- Works offline

## Slide Structure

```html
<!DOCTYPE html>
<html>
<head>
  <style>
    .slide { 
      width: 100vw; 
      height: 100vh; 
      display: none;
      padding: 5vh 5vw;
    }
    .slide.active { display: flex; }
  </style>
</head>
<body>
  <div class="slide active" id="slide1">
    <!-- Content -->
  </div>
  <div class="slide" id="slide2">
    <!-- Content -->
  </div>
  <script>
    // Arrow key navigation
    let current = 0;
    const slides = document.querySelectorAll('.slide');
    document.addEventListener('keydown', (e) => {
      if (e.key === 'ArrowRight') next();
      if (e.key === 'ArrowLeft') prev();
    });
    function next() {
      slides[current].classList.remove('active');
      current = (current + 1) % slides.length;
      slides[current].classList.add('active');
    }
    function prev() {
      slides[current].classList.remove('active');
      current = (current - 1 + slides.length) % slides.length;
      slides[current].classList.add('active');
    }
  </script>
</body>
</html>
```

## Animation Patterns

### Fade In
```css
@keyframes fadeIn {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}
.animate { animation: fadeIn 0.5s ease-out; }
```

### Stagger Children
```css
.stagger > *:nth-child(1) { animation-delay: 0.1s; }
.stagger > *:nth-child(2) { animation-delay: 0.2s; }
.stagger > *:nth-child(3) { animation-delay: 0.3s; }
```

## PPTX Conversion Guide
1. Export slides as images
2. Create HTML wrapper
3. Add navigation controls
4. Enhance with CSS animations
5. Single file output

## Output
Single `presentation.html` file ready to open in browser.
