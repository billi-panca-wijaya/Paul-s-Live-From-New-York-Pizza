# 🍕 Paul's Live From New York Pizza

A high-performance, SEO-optimized website built with **Astro** and **Svelte** for Paul's Live From New York Pizza - an authentic New York-style pizza restaurant serving Humboldt County, California.

![Astro](https://img.shields.io/badge/Astro-4.x-FF5D01?style=flat-square&logo=astro&logoColor=white)
![Svelte](https://img.shields.io/badge/Svelte-4.x-FF3E00?style=flat-square&logo=svelte&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)

## 🌐 Live Website

**Production URL:** [https://paulslivefromnewyorkpizza.com/](https://paulslivefromnewyorkpizza.com/)

## ✨ Features

### Performance First
- ⚡ **Astro Islands Architecture** - Minimal JavaScript by default
- 🚀 **Static Rendering** - Pre-rendered HTML for instant loading
- 🖼️ **Optimized Images** - Lazy loading with proper dimensions
- 📦 **Small Bundle Size** - Only hydrates interactive components

### SEO Optimized
- 🔍 **Unique Meta Tags** - Custom title and description per page
- 🔗 **Canonical URLs** - Proper canonical tags on all pages
- 🗺️ **Auto Sitemap** - Generated sitemap.xml for search engines
- 🤖 **robots.txt** - Configured for optimal crawling
- 📊 **Schema.org** - Structured data for local business

### Modern UX/UI
- 📱 **Fully Responsive** - Mobile-first design
- 🎨 **Premium Design** - Modern aesthetics with smooth animations
- ♿ **Accessible** - Respects `prefers-reduced-motion`
- 🍔 **Mobile Navigation** - Hamburger menu for mobile devices

### Core Web Vitals
- **LCP** < 2.5s - Optimized hero images
- **CLS** ~ 0 - Reserved space for dynamic content
- **INP** < 200ms - Minimal JavaScript interaction

## 📁 Project Structure

```
├── public/
│   ├── favicon.svg          # SVG favicon (white F on black)
│   └── robots.txt            # SEO robots configuration
├── src/
│   ├── components/
│   │   ├── Navigation.svelte # Interactive mobile menu
│   │   ├── ContactForm.svelte # Reservation form
│   │   ├── LazyMap.svelte    # Click-to-load maps
│   │   ├── Hero.astro        # Hero section
│   │   ├── Footer.astro      # Site footer
│   │   ├── LocationCard.astro # Location display
│   │   ├── MenuSection.astro # Menu category
│   │   └── MenuItem.astro    # Individual menu item
│   ├── layouts/
│   │   └── BaseLayout.astro  # Base HTML with SEO
│   ├── pages/
│   │   ├── index.astro       # Homepage
│   │   ├── menu.astro        # Full menu
│   │   ├── locations.astro   # Store locations
│   │   ├── about.astro       # About page
│   │   ├── contact.astro     # Contact & reservations
│   │   └── 404.astro         # Custom 404 page
│   └── styles/
│       └── global.css        # Global styles & CSS variables
├── astro.config.mjs          # Astro configuration
├── package.json
└── tsconfig.json
```

## 🚀 Getting Started

### Prerequisites

- Node.js 18+ 
- npm or pnpm

### Installation

```bash
# Clone the repository
git clone https://github.com/bilynatalia/Paul-s-Live-From-New-York-Pizza.git

# Navigate to project
cd Paul-s-Live-From-New-York-Pizza

# Install dependencies
npm install

# Start development server
npm run dev
```

### Available Scripts

| Command | Description |
|---------|-------------|
| `npm run dev` | Start development server at `localhost:4321` |
| `npm run build` | Build production site to `./dist/` |
| `npm run preview` | Preview production build locally |

## 📄 Pages

| Route | Description |
|-------|-------------|
| `/` | Homepage with hero, featured menu, and locations preview |
| `/menu` | Complete menu with all pizza categories, salads, entrees |
| `/locations` | Three store locations with lazy-loaded Google Maps |
| `/about` | Restaurant story and values |
| `/contact` | Contact information and reservation form |
| `/404` | Custom branded 404 page with animations |

## 🎨 Design System

### Colors

```css
--color-pizza-red: #D32F2F    /* Primary brand color */
--color-pizza-dark: #1A1A1A   /* Dark backgrounds */
--color-pizza-gold: #FBC02D   /* Accent/highlight */
--color-off-white: #F9F9F9    /* Light backgrounds */
```

### Typography

- **Headings:** Oswald (Google Fonts)
- **Body:** Roboto (Google Fonts)

## 🏪 Locations

1. **Arcata** - 665 Samoa Blvd, Arcata, CA 95521 - (707) 822-6199
2. **Eureka** - 604 F St, Eureka, CA 95501 - (707) 442-5800
3. **Fortuna** - 101 12th Street, Fortuna, CA 95540 - (707) 725-1123

## 🔧 Technology Stack

- **Framework:** [Astro](https://astro.build/) v4.x
- **UI Components:** [Svelte](https://svelte.dev/) v4.x
- **Styling:** Vanilla CSS with CSS Custom Properties
- **Sitemap:** @astrojs/sitemap
- **Fonts:** Google Fonts (Oswald, Roboto)

## 📈 Performance Optimizations

- ✅ Pre-rendered static HTML pages
- ✅ Font preloading with `font-display: swap`
- ✅ Lazy loading images with dimensions
- ✅ Click-to-load Google Maps (never blocks render)
- ✅ Minimal client-side JavaScript
- ✅ CSS animations with `prefers-reduced-motion` support
- ✅ Inline critical CSS

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License.

---

**Built with ❤️ using Astro + Svelte**