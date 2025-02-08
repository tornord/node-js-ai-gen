# Project Setup

## Overview
This document provides a comprehensive guide to set up the project. The project is based on Node JS 22.13.1 tech stack and includes various tools and libraries to ensure a robust development environment.

## Tech stack
- NPM as package manager
- TypeScript as programming language
- React as UI library
- Vite as build tool and development server
- Vitest as testing framework
- React testing library as React components testing library
- React Router as client-side routing
- Emotion React as styling solution
- Prettier as code formatter
- ESLint as code linter
- Storybook for component library

## Design details
- Set type to `module` in `package.json`
- Add global styles in `src/main.tsx`, base project font should be defined in global styles
- Vite and Vitest should use same config file `vite.config.ts`
- Add styling by using Styled Components, do not use css prop in React components
- Add a VS Code launch configuration `Run current file` to `.vscode/launch.json`
- Use `tsx` (as `node --import=tsx/esm`) to start own server side typescript files
- Set `target` to `esnext` in `tsconfig.json`
- Add `README.md` file and add how to install and run the project
- When adding tests, put them in same folder as the file you are testing
- Add a simple Home page as a start and add a test for it
- Add typescript support for eslint
- Install storybook by running `npm init storybook`
- When adding storybook stories, put them in same folder as the component

## Project Structure
- `src/` - Contains the main application code
  - `components/` - Reusable UI components
  - `pages/` - Route-specific pages
  - `utils/` - Utility functions and helpers
  - `App.tsx` - Root component
  - `main.tsx` - Entry point for the application. Add extra check for root element
- `server/` - Contains the server side code
- `docs/` - Folder for documentation
- `public/` - Static assets
- `vite.config.ts` - Vite and Vitest configuration
- `tsconfig.json` - TypeScript configuration
- `tsconfig.node.json` - TypeScript configuration for vite.config and `server/`
- `package.json` - Project dependencies and scripts
- `index.html` - HTML entry point, Add link to base project font
- `.eslintrc.cjs` - ESLint configuration
- `.nvmrc` - Node version here
- `.gitignore` - Git ignore
- `.env` always use this file for secrets and environment variables

## Notes
- The base project font is Roboto from Google Fonts.

## Getting Started
1. Clone the repository:
   ```sh
   git clone <repository-url>
   cd <repository-directory>
   ```

2. Install dependencies:
   ```sh
   npm install
   ```

3. Start the development server:
   ```sh
   npm run dev
   ```

4. Run tests:
   ```sh
   npm run test
   ```

5. Build the project:
   ```sh
   npm run build
   ```

6. Start the server:
   ```sh
   npm run start
   ```

7. Launch Storybook:
   ```sh
   npm run storybook
   ```
