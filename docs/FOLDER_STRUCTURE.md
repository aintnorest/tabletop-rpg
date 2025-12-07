# Folder Structure Documentation

This document explains the folder structure of the tabletop-rpg project and how it enforces DRY (Don't Repeat Yourself) principles. The structure follows SvelteKit standards while maintaining clear boundaries for where different types of files should live.

## Root Directory

### Configuration Files
- `package.json` - Project dependencies and npm scripts
- `svelte.config.js` - SvelteKit configuration (adapters, paths, prerendering)
- `vite.config.ts` - Vite build tool configuration
- `tsconfig.json` - TypeScript compiler configuration
- `.gitignore` - Files and directories to exclude from version control
- `README.md` - Project overview and quick start guide

## Source Directory (`src/`)

### Application Structure

#### `src/routes/`
**Purpose**: File-based routing system. Each file/folder here represents a route in the application.

**File Naming Conventions**:
- `+page.svelte` - The page component for a route
- `+layout.svelte` - Layout component that wraps routes
- `+page.ts` / `+page.server.ts` - Data loading for pages
- `+layout.ts` / `+layout.server.ts` - Data loading for layouts
- `+error.svelte` - Error pages for specific routes

**DRY Principle**: Routes are automatically generated from the file structure. No manual route configuration needed.

**Example Structure**:
```
src/routes/
├── +page.svelte              # Home page (/)
├── +layout.svelte            # Root layout (applies to all routes)
├── rules/
│   ├── +page.svelte          # /rules page
│   └── +layout.svelte        # Layout specific to rules section
└── character-builder/
    └── +page.svelte          # /character-builder page
```

#### `src/lib/`
**Purpose**: Reusable code that can be imported anywhere in the application.

**What Goes Here**:
- Utility functions (`src/lib/utils.ts`, `src/lib/helpers.ts`)
- Reusable Svelte components (`src/lib/components/`)
- Type definitions (`src/lib/types.ts`)
- Constants and configuration (`src/lib/constants.ts`)
- Business logic modules

**DRY Principle**: Code placed here can be imported and reused across multiple routes/components without duplication.

**Example Structure**:
```
src/lib/
├── components/               # Reusable Svelte components
│   ├── Button.svelte
│   └── Card.svelte
├── utils/                    # Utility functions
│   ├── formatting.ts
│   └── validation.ts
├── types/                    # TypeScript type definitions
│   └── game.ts
└── constants/                # Application constants
    └── game-rules.ts
```

#### `src/stores/`
**Purpose**: Svelte stores for global state management.

**What Goes Here**:
- Writable stores for mutable state
- Readable stores for derived state
- Custom store implementations

**DRY Principle**: State is defined once and can be accessed from any component without prop drilling.

**Example Structure**:
```
src/stores/
├── character.ts              # Character state store
└── game-state.ts             # Game state store
```

#### `src/assets/`
**Purpose**: Static assets that need to be processed by Vite (e.g., images, fonts).

**What Goes Here**:
- Images (`.png`, `.jpg`, `.svg`, etc.)
- Fonts (`.woff`, `.woff2`, `.ttf`, etc.)
- Other assets that need optimization/processing

**Note**: Import assets from this directory in your code, don't reference them by path. Vite will process and optimize them.

#### `src/app.d.ts`
**Purpose**: TypeScript type definitions for app-wide types.

**What Goes Here**:
- `App` namespace type augmentations
- Global type declarations
- Interface definitions for SvelteKit features

**DRY Principle**: App-wide types are defined in one place.

#### `src/app.html`
**Purpose**: HTML template for the application.

**What Goes Here**:
- Base HTML structure
- Meta tags
- SvelteKit template variables (`%sveltekit.head%`, `%sveltekit.body%`)

**Note**: This is the template that wraps all pages. Only modify if you need to change the base HTML structure.

#### `src/app.css`
**Purpose**: Global CSS styles.

**What Goes Here**:
- CSS resets
- Global styles (fonts, colors, etc.)
- CSS variables/design tokens
- Utility classes that apply globally

**DRY Principle**: Global styles defined once apply everywhere. Component-specific styles should be in component `<style>` blocks.

## Static Directory (`static/`)

**Purpose**: Files served as-is without processing.

**What Goes Here**:
- `favicon.png` / `favicon.ico`
- `robots.txt`
- `sitemap.xml`
- `.nojekyll` (for GitHub Pages)
- Any other files that need to be accessible at the root URL

**DRY Principle**: Static files are copied directly to the build output. Reference them using paths starting with `/` (e.g., `/favicon.png`).

## Documentation Directory (`docs/`)

**Purpose**: Project documentation.

**What Goes Here**:
- Architecture decisions
- API documentation
- Folder structure documentation (this file)
- Development guides
- User guides (for game rules, character builder, etc.)

## GitHub Actions (`.github/workflows/`)

**Purpose**: CI/CD automation.

**What Goes Here**:
- `deploy.yml` - Automated deployment workflow
- Other workflows as needed (testing, linting, etc.)

## Build Output (`build/`)

**Purpose**: Generated directory containing the built application.

**Note**: This directory is created by the build process and should not be edited manually. It's excluded from version control.

## DRY Principles in Practice

### 1. Single Source of Truth
- Components live in `src/lib/components/` - import once, use anywhere
- Types live in `src/lib/types/` - define once, use everywhere
- Utilities live in `src/lib/utils/` - write once, import where needed

### 2. Clear Boundaries
- Route-specific code → `src/routes/[route-name]/`
- Shared/reusable code → `src/lib/`
- Global state → `src/stores/`
- Static files → `static/`

### 3. Convention Over Configuration
- File names determine routes (`+page.svelte` = route)
- Directory structure determines imports (`src/lib/utils.ts` = `$lib/utils`)
- No ambiguous locations - if you're not sure where something goes, this doc should answer it

## Adding New Features

### Adding a New Route
1. Create a new folder/file in `src/routes/` following SvelteKit conventions
2. Add a `+page.svelte` file
3. Optionally add route-specific layout, data loading, etc.

### Adding a Reusable Component
1. Create component in `src/lib/components/`
2. Import using `$lib/components/ComponentName.svelte`
3. Use across multiple routes as needed

### Adding a Utility Function
1. Add to appropriate file in `src/lib/utils/` or create new file
2. Export the function
3. Import using `$lib/utils/[filename]`

### Adding Global State
1. Create a store file in `src/stores/`
2. Export the store
3. Import and use in any component

## Questions?

If you're unsure where a file should live:
1. Check this document first
2. Ask: "Is this used in one place or multiple places?"
   - One place → route-specific location
   - Multiple places → `src/lib/`
3. Ask: "Does this need to be processed by the build?"
   - Yes → `src/assets/` (if imported) or `static/` (if referenced by path)
   - No → `static/`

