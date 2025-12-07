# Tabletop RPG

A website for displaying rules and lore for a tabletop role-playing game, with tools for character building and gameplay.

## Tech Stack

- **Framework**: SvelteKit
- **Language**: TypeScript
- **Deployment**: GitHub Pages

## Project Status

Currently in development. The site displays a placeholder landing page.

## Setup

### Prerequisites

- Node.js 20 or higher
- npm

### Installation

1. Clone the repository:
```bash
git clone git@github.com:aintnorest/tabletop-rpg.git
cd tabletop-rpg
```

2. Install dependencies:
```bash
npm install
```

3. Run the development server:
```bash
npm run dev
```

The site will be available at `http://localhost:5173`

### Building for Production

```bash
npm run build
```

The built files will be in the `build/` directory.

### Preview Production Build

```bash
npm run preview
```

## Development

### Project Structure

See [docs/FOLDER_STRUCTURE.md](docs/FOLDER_STRUCTURE.md) for detailed documentation on the project structure and where files should be placed.

### Key Principles

- **DRY (Don't Repeat Yourself)**: Code should be written once and reused. See the folder structure documentation for guidance on where files should live.
- **YAGNI (You Aren't Gonna Need It)**: Only build what's necessary for the current acceptance criteria.
- **Clear Boundaries**: Each directory has a specific purpose to prevent ambiguity about where files belong.

## Deployment

The project is automatically deployed to GitHub Pages via GitHub Actions when changes are pushed to the `main` branch.

The site is available at: https://aintnorest.github.io/tabletop-rpg

## Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build
- `npm run check` - Run Svelte type checking
- `npm run check:watch` - Run Svelte type checking in watch mode

