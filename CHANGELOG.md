# Changelog

All notable changes to this project will be documented in this file.

## [1.2.0] - 2026-04-18
### Added
- **Hero Variations**: Added `HeroSplit.astro` and `HeroMinimal.astro` components.
- **Profile Picture Support**: Integrated image upload in Payload CMS `HomePage` global and display on the frontend.
- **Alternative Design Instructions**: Documentation in README for swapping Hero styles.

### Changed
- **Brighter Theme**: Redesigned the entire site with a Light-mode aesthetic using Tailwind CSS v4.
- **Color Palette Update**: Switched to off-white backgrounds, soft pastel gradients, and crisp slate typography.
- **Glassmorphism Refresh**: Updated glass utilities for a cleaner, light-background look.

## [1.1.0] - 2026-04-17
### Added
- **Payload Globals**: Migrated hardcoded page content to Payload CMS Globals (`HomePage`, `AboutPage`, `ProjectsPage`).
- **Dynamic About Page**: Added a Lexical rich-text editor for the About page content.
- **About Page Integration**: Created `about.astro` and connected it to the CMS.

### Fixed
- **Navigation Links**: Fixed the "About" button in navigation to point to a discrete page rather than an anchor tag.
- **Turbopack Resolving**: Fixed Next.js package resolution in Bun Workspaces for Turbopack.
- **Payload Import Map**: Resolved component missing errors in Payload Admin by generating a runtime import map.

## [1.0.0] - 2026-04-15
### Added
- **Initial Monorepo Setup**: Configured Bun Workspaces with `/frontend` (Astro) and `/cms` (Payload).
- **SQLite Database**: Set up local SQLite adapter for Payload CMS.
- **Astro Frontend**: Initialized Astro with Tailwind CSS v4.
- **Project Structure**: Created `Projects` collection and `Profile` global.
- **Core Components**: Implemented `Header`, `Footer`, `Hero`, and `ProjectCard`.
- **API Fetching**: Built `lib/api.ts` for Payload REST API consumption.
- **Base Layout**: Premium dark-mode design with glassmorphism effects.
- **Documentation**: Initial README and .gitignore setup.
