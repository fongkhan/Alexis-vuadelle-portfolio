# Alexis Vuadelle's Portfolio Repository 🚀

This repository contains the source code for a dynamic, high-performance portfolio built with **Astro**, **Tailwind CSS**, and **Payload CMS**. 

The project is structured as a Bun Workspace containing two separate applications that communicate together.

## 📁 Repository Structure

- `frontend/` - The visual Astro website using Tailwind CSS for a premium, brighter responsive design.
- `cms/` - The headless Payload CMS backend running on Next.js, powered by a local SQLite database.

---

## 🎨 Bright Theme & Dynamic Content

The portfolio has been recently updated with a **Bright/Light-mode aesthetic**.
- **Clean UI**: Uses a soft off-white background with vibrant pastel gradients and crisp dark typography.
- **Payload Globals**: The text for the Home, About, and Projects pages is now managed entirely through Payload CMS Globals. No more hardcoded strings!
- **Profile Picture**: Supported via the `HomePage` global in the CMS.

## 🚀 Hero Component Variations

We've implemented three different Hero section designs that you can swap between easily:

1.  **Default Hero**: Centered layout with a large avatar above the text.
2.  **Split Hero**: Modern side-by-side layout with text on the left and a floating image card on the right.
3.  **Minimal Hero**: Clean, text-focused layout with a small circular profile icon.

### How to Change the Hero Design
1.  Open `frontend/src/pages/index.astro`.
2.  Locate the import section at the top.
3.  Comment out the current `Hero` import and uncomment the variation you want to try:
    ```typescript
    // Default
    import Hero from '../components/Hero.astro';
    
    // Split Variation
    // import Hero from '../components/HeroSplit.astro';
    
    // Minimal Variation
    // import Hero from '../components/HeroMinimal.astro';
    ```

---

## 🛠️ Getting Started: How to View the Site Locally

To run the full stack locally, you need to start **both** applications in development mode simultaneously.

### Step 1: Install Dependencies
```bash
# In the root directory of the repository
bun install
```

### Step 2: Start the Payload CMS Backend
```bash
cd cms
bun run dev
```
The CMS starts on **`http://localhost:3000`**.  
Visit `http://localhost:3000/admin` to manage your **Globals** (Home, About, Projects) and **Collections** (Projects, Media).

### Step 3: Start the Astro Frontend
```bash
cd frontend
bun run dev
```
The website starts on **`http://localhost:4321`**.

---

## Technical Details

- **Database**: SQLite (Local file at `/cms/payload.db`).
- **CSS**: Tailwind CSS v4.
- **Runtime**: Bun.
