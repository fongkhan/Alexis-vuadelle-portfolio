# Changelog

All notable changes to this project will be documented in this file.

## [Unreleased]

### Added
- **Global Background Animation:** Integrated three fluid, drifting HTML background blobs with heavy CSS matrix blurs via `@keyframes` floating animations across `Layout.astro` and `global.css` for a layered glassmorphism aesthetic.
- **SSR Adapter (`frontend`):** Included `@astrojs/node` in standalone mode so the frontend can dynamically respond to endpoints without static rebuilds.
- **Custom Passenger Boot Scripts:** Designed discrete `server.js` entry files inside both `/frontend` and `/cms` exclusively for Phusion Passenger compatibility on O2Switch shared-hosting architectures.

### Changed
- **Database:** Swapped the generic Payload SQLite adapter (`@payloadcms/db-sqlite`) completely out for a high-performance strictly-typed PostgreSQL adapter (`@payloadcms/db-postgres`) tailored for production scale.
- **Hero Component Redesign (`Hero.astro`):** Overhauled the central index hero module into an aggressive Split Two-Column layout, positioning the primary textual content on the left and a 3D-rotated, glassmorphism-framed profile image on the right. 
- **Responsive Navigation Fixes:** Appended aggressive `pt-48` padding constraints onto Mobile viewports to actively prevent overlap beneath the floating header "island".
- **Anchor Offset Fixes:** Appended `scroll-mt-32` spacing variables onto all primary navigation endpoints (`#projects`, `#career`, `#contact`) assuring that when navigating between sections natively, the target anchor avoids occlusion beneath the floating `#navbar-island`.

### Fixed
- **iPad Viewport Scaling:** Modified the global CSS `.section-container` class to enforce `px-12` until hitting `xl:px-0` bounds. This safely restored horizontal breathing room on iPads and tablets where text was previously crashing directly into the structural edges.
- **Excessive Component Margins:** Removed fixed `min-h-[70vh]` height assertions globally across `CareerSection` and `ProjectsSection`, reverting components to dynamic `py-24` boundaries. Eliminates the visually excessive arbitrary "empty space" below minimal content streams.
