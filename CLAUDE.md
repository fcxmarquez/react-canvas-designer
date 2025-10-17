# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a React-Vite template designed as a safe prototyping environment for code agents to quickly test ideas and concepts. The focus is on building a **global Design System** with emphasis on the visual layer only—no business logic, API connections, or complex state management.

## Tech Stack

- **React 19** with TypeScript
- **Vite** for build tooling
- **Tailwind CSS v4** for styling
- **Radix UI Primitives** for accessible component foundations
- **Framer Motion** for animations
- **React Router** (v7) for route management
- **Storybook** for component development and documentation

## Essential Commands

### Package Management
```bash
pnpm install           # Install dependencies
```

### Development
```bash
pnpm dev              # Start Vite dev server
pnpm storybook        # Start Storybook on port 6006
```

### Building
```bash
pnpm build            # TypeScript check + Vite build
pnpm build-storybook  # Build Storybook for deployment
pnpm preview          # Preview production build
```

### Code Quality
```bash
pnpm lint             # Run ESLint
pnpm lint:fix         # Auto-fix ESLint issues
pnpm format           # Format code with Prettier
pnpm format:check     # Check code formatting
```

## Architecture

### Routing
- React Router is configured in `src/routes/index.tsx`
- Main application entry is `src/main.tsx` which uses `RouterProvider`
- Root route (`/`) renders the `App` component

### Component Organization
- **Production components**: Place in `src/` with appropriate subdirectories
- **Storybook examples**: Located in `src/stories/` (Button, Header, Page examples provided)
- All stories follow the pattern `*.stories.ts` alongside their component files
- Stories are auto-discovered by Storybook config in `.storybook/main.ts`

### Styling Approach
- Use **Tailwind CSS v4** utility classes for all styling
- For component variants (sizes, colors), use the `cva()` utility
- No inline styles unless absolutely necessary
- Component-specific CSS files only when Tailwind is insufficient

## Development Workflow

1. **Views development**: Develop the first prototype directly into the `App.tsx` file. After that, you have the freedom to develop the rest of the views and components as you see fit.
2. **Components development**: If needed, develop components in the `src/components` directory.
3. **Build testing**: Ensure TypeScript compilation passes (`pnpm build`)

## Development Guidelines
- You are free to use and install any library if is needed for the current task.