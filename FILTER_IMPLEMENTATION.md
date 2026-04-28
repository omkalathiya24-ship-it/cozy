# Luxury Filter Overlay System

## Overview
The Filter Overlay System replaces the traditional sidebar filters with a sophisticated, full-screen image-based overlay. It is designed to maintain a luxury aesthetic while providing a highly functional and accessible interface for product discovery.

## Key Features

### 1. Image-Triggered Entry
- **Trigger**: A clickable thumbnail/icon button located above the product grid.
- **Visual Feedback**: The trigger changes state (dark background) when the filter is active.
- **Image Fallback**: If the luxury filter image fails to load, the system automatically falls back to a minimalist slider icon.

### 2. Immersive Overlay Interface
- **Smooth Transitions**: Uses Angular's `trigger`, `transition`, and `animate` with `cubic-bezier` timing for a fluid fade-and-scale effect.
- **Backdrop Blur**: Utilizes `backdrop-filter: blur(10px)` to create a high-end glassmorphism effect, focusing user attention on the refinement options.
- **Scroll Locking**: The body scroll is automatically locked when the overlay is active to prevent background scrolling.

### 3. Refinement Options
- **Categorization**: Multi-column layout for Categories, Subcategories, Gender, and Sizes.
- **Filter Pills**: Interactive buttons that change state when selected.
- **Luxury Price Range**: A clean, typography-focused price input system using the `Libre Caslon Display` and `Libre Baskerville` fonts.
- **Live Counting**: The "Show Results" button dynamically updates with the count of filtered products.

### 4. Accessibility & Performance
- **Keyboard Support**: Users can close the overlay using the `Escape` key.
- **ARIA Compliance**: Includes proper roles (`dialog`, `button`), labels (`aria-label`), and modal state management (`aria-modal`).
- **Responsive Design**: Adapts from a 4-column layout on desktop to a single-column scrollable interface on mobile.
- **Optimized Rendering**: Uses 4:5 aspect ratios for product images and `object-fit: cover` for a consistent, premium look.

## Implementation Details

### Files
- **Component**: `menu.component.ts` (Logic & Animations)
- **Template**: `menu.component.html` (Overlay Structure & ARIA)
- **Styling**: `menu.component.css` (Luxury UI & Transitions)
- **Service**: `shop.service.ts` (Global State Management)

### Animations
The overlay uses a scale and fade animation:
```typescript
trigger('overlayAnimation', [
  state('void', style({ opacity: 0, transform: 'scale(1.05)' })),
  state('*', style({ opacity: 1, transform: 'scale(1)' })),
  transition('void <=> *', [ animate('400ms cubic-bezier(0.4, 0, 0.2, 1)') ])
])
```

### Accessibility Logic
A `HostListener` is used to capture global keyboard events:
```typescript
@HostListener('window:keydown.escape', ['$event'])
onEscapeKeydown(event: KeyboardEvent) {
  if (this.showFilters) { this.closeFilters(); }
}
```
