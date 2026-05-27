# Promotional Card HTML Structure & Styling Guide

## HTML Structure

```html
<!-- PROMOTION CARD -->
<section class="promo-banner">
  <div class="promo-card">
    <!-- Badge -->
    <div class="promo-badge-top">🎉 Opening Special Offer</div>
    
    <!-- Main Content: Text + Highlight Box -->
    <div class="promo-content">
      <div class="promo-text-main">
        <h2 class="promo-title">
          <span class="amharic">እሁድን ከኛ ጋር ያሳልፉ፣</span>
          <span class="english">Spend Sunday with Us,</span>
        </h2>
        <p class="promo-subtitle">
          <span class="amharic">ሁሉንም ምግቦች በ</span>
          <span class="english">All Foods at</span>
          <span class="highlight">£10</span>
        </p>
        <p class="promo-date">
          <span class="amharic">ግንቦት 23</span> (May 23) | <span class="gregorian-date">Gregorian Calendar</span>
        </p>
      </div>
      
      <!-- Highlight Box: Featured Item -->
      <div class="promo-highlight-box">
        <div class="promo-highlight-icon">🐟</div>
        <div class="promo-highlight-text">
          <p class="promo-highlight-title">Fish Buffet</p>
          <p class="promo-highlight-desc">
            <span class="amharic">የፍስክ ቡፌ</span>
          </p>
        </div>
      </div>
    </div>
    
    <!-- Call-to-Action -->
    <div class="promo-cta">
      <p class="promo-cta-text">
        <span class="amharic">ቅበላን ከኛ ጋር</span>
        <span class="english">Join us for an unforgettable dining experience!</span>
      </p>
    </div>
    
    <!-- Decorative Sparkles -->
    <div class="promo-decoration">
      <div class="promo-spark spark-1"></div>
      <div class="promo-spark spark-2"></div>
      <div class="promo-spark spark-3"></div>
      <div class="promo-spark spark-4"></div>
    </div>
  </div>
</section>
```

---

## CSS Animations

### 1. slideInDown (Entry Animation)
```css
@keyframes slideInDown {
  from {
    opacity: 0;
    transform: translateY(-30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
```
**Applied to**: `.promo-banner`
**Duration**: 0.8s ease-out

---

### 2. float (Gentle Movement)
```css
@keyframes float {
  0%, 100% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(-12px);
  }
}
```
**Applied to**: 
- `.promo-text-main` (4s infinite)
- `.promo-highlight-box` (5s infinite, 0.5s delay)

---

### 3. pulse-scale (Pulsing Effect)
```css
@keyframes pulse-scale {
  0%, 100% {
    transform: scale(1);
    opacity: 1;
  }
  50% {
    transform: scale(1.08);
    opacity: 0.8;
  }
}
```
**Applied to**:
- `.promo-badge-top` (2s infinite)
- `.promo-highlight-icon` (2s infinite)
- `.promo-subtitle .highlight` (2.5s infinite, 0.3s delay)

---

### 4. sparkle (Particle Effect)
```css
@keyframes sparkle {
  0% {
    opacity: 0;
    transform: translate(0, 0) scale(0);
  }
  50% {
    opacity: 1;
  }
  100% {
    opacity: 0;
    transform: translate(var(--tx), var(--ty)) scale(1);
  }
}
```
**Applied to**: `.promo-spark` elements with custom `--tx` and `--ty` variables
- spark-1: 2s infinite
- spark-2: 2.5s infinite (0.3s delay)
- spark-3: 2.2s infinite (0.6s delay)
- spark-4: 2.8s infinite (0.9s delay)

---

## Styling Classes

### Main Container
```css
.promo-banner {
  background: linear-gradient(135deg, #fff5e6 0%, #ffe8cc 50%, #ffd9a3 100%);
  padding: 20px 1.5rem;
  animation: slideInDown 0.8s ease-out;
}

.promo-card {
  background: linear-gradient(135deg, #fff8f0 0%, #ffffff 100%);
  border: 2px solid #e8c97a;
  border-radius: 16px;
  padding: 28px;
  box-shadow: 0 12px 40px rgba(200, 100, 43, 0.2);
}
```

### Badge
```css
.promo-badge-top {
  background: linear-gradient(135deg, #c0392b, #e74c3c);
  color: #fff;
  padding: 6px 16px;
  border-radius: 30px;
  font-weight: 800;
  animation: pulse-scale 2s ease-in-out infinite;
}
```

### Title & Text
```css
.promo-title {
  font-size: clamp(1.4rem, 4vw, 2rem);
  font-weight: 800;
  display: flex;
  flex-direction: column;
}

.promo-title .amharic {
  color: #c0392b;
  font-weight: 900;
}

.promo-title .english {
  color: #1a0a0a;
  font-weight: 800;
}
```

### Highlight Box (Feature Item)
```css
.promo-highlight-box {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 12px;
  background: linear-gradient(135deg, rgba(192, 57, 43, 0.1), rgba(232, 201, 122, 0.1));
  border: 2px dashed #e8c97a;
  border-radius: 12px;
  padding: 20px;
  min-width: 140px;
  animation: float 5s ease-in-out infinite 0.5s;
}

.promo-highlight-icon {
  font-size: 3rem;
  animation: pulse-scale 2s ease-in-out infinite;
}
```

### Price Highlight
```css
.promo-subtitle .highlight {
  display: inline-block;
  background: linear-gradient(135deg, #c0392b, #e74c3c);
  color: #fff;
  padding: 4px 14px;
  border-radius: 8px;
  font-weight: 900;
  font-size: 1.2em;
  animation: pulse-scale 2.5s ease-in-out infinite 0.3s;
}
```

### Call-to-Action
```css
.promo-cta {
  background: linear-gradient(135deg, rgba(192, 57, 43, 0.08), rgba(232, 201, 122, 0.1));
  border-left: 4px solid #c0392b;
  padding: 16px 16px;
  border-radius: 8px;
}
```

---

## Responsive Design

### Mobile (max-width: 768px)
```css
.promo-content {
  grid-template-columns: 1fr;  /* Stack vertically */
  gap: 20px;
}

.promo-highlight-box {
  min-width: 100%;  /* Full width */
  flex-direction: row;  /* Side-by-side layout */
}

.promo-title {
  font-size: 1.2rem;
}
```

---

## Color System

| Element | Color | Usage |
|---------|-------|-------|
| Primary Red | #c0392b | Amharic text, badges, accents |
| Light Red | #e74c3c | Gradients, highlights |
| Gold | #e8c97a | Borders, decorative elements |
| Warm Cream | #fff5e6-#ffd9a3 | Banner background gradient |
| Off-white | #fff8f0-#ffffff | Card background gradient |
| Text | #1a0a0a | Main text color |
| Muted | var(--text-muted) | Secondary text |

---

## Animation Timing Strategy

**Staggered Timing for Visual Interest:**
- Badge: 2s (starts immediately)
- Price highlight: 2.5s (0.3s delay)
- Fish icon: 2s (synchronized with badge)
- Fish box: 5s (0.5s delay, slower movement)
- Title: 4s (slower, continuous float)
- Sparkles: 2-2.8s (0.3s-0.9s delays, random burst effect)

This creates a smooth, choreographed animation sequence without overwhelming the viewer.

---

## Bilingual Text Support

### Amharic Elements
- Title: "እሁድን ከኛ ጋር ያሳልፉ፣" (Spend Sunday with Us)
- Subtitle: "ሁሉንም ምግቦች በ" (All Foods at)
- Date: "ግንቦት 23" (May 23)
- Feature: "የፍስክ ቡፌ" (Fish Buffet)
- CTA: "ቅበላን ከኛ ጋር" (Join us with us)

### English Elements
- "Spend Sunday with Us,"
- "All Foods at"
- "(May 23) | Gregorian Calendar"
- "Fish Buffet"
- "Join us for an unforgettable dining experience!"

---

## Browser Compatibility

All animations use standard CSS3:
- ✅ Chrome/Edge (fully supported)
- ✅ Firefox (fully supported)
- ✅ Safari (fully supported)
- ✅ Mobile browsers (optimized)

Hardware acceleration is enabled through `transform` and `opacity` properties.

---

## Customization Guide

### To Change Colors:
Edit in `style.css`:
```css
.promo-banner {
  background: linear-gradient(135deg, #YOUR_COLOR1, #YOUR_COLOR2);
}
```

### To Adjust Animation Speed:
```css
.promo-text-main {
  animation: float 4s ease-in-out infinite;  /* Change 4s to desired duration */
}
```

### To Add/Remove Sparkles:
Add more `.promo-spark` elements with unique classes:
```html
<div class="promo-spark spark-5"></div>
```

And define animation timing in CSS:
```css
.spark-5 {
  left: 30%;
  top: 50%;
  animation: sparkle 3s ease-out infinite 1.2s;
}
```

---

**Status**: ✅ Production Ready | 🎨 Fully Customizable | 📱 Responsive
