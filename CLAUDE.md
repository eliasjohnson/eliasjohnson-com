# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Commands

```bash
# Install dependencies (use pnpm)
pnpm install

# Start development server
pnpm dev                # Runs on http://localhost:5173
pnpm dev -- --open      # Opens browser automatically

# Type checking
pnpm check              # One-time type check
pnpm check:watch        # Watch mode for continuous checking

# Build for production
pnpm build              # Creates static site in build/

# Preview production build
pnpm preview            # Test the built site locally

# Local tunneling for external testing
ngrok http 5173         # Useful for mobile testing
```

## High-Level Architecture

This is a SvelteKit 5 portfolio website deployed to GitHub Pages at 3lias.pro.

### Tech Stack
- **Framework**: SvelteKit 5 with TypeScript
- **Build Tool**: Vite 6
- **Package Manager**: pnpm (required)
- **Deployment**: GitHub Pages via GitHub Actions
- **Styling**: CSS-in-Svelte components

### Project Structure
- `src/routes/+page.svelte` - Main portfolio page with all sections (hero, nav, experience, education, projects)
- `src/routes/+page.ts` - Page load configuration with prerendering enabled
- `static/` - Static assets served directly
- `build/` - Production output (git-ignored)
- GitHub Actions workflow handles automatic deployment on push to main

### Key Configuration
- **Base Path**: `/eliasjohnson-com` configured for GitHub Pages
- **Adapter**: Static adapter for generating static HTML/CSS/JS
- **TypeScript**: Strict mode enabled
- **Vite**: Configured to allow ngrok tunneling

### Development Patterns
- All components are currently inline within route files
- Heavy use of CSS animations and transitions
- Intersection Observer for scroll-triggered animations
- Responsive design with CSS Grid and Flexbox
- Professional card-based layouts for content sections