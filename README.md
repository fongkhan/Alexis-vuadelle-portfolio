# Alexis Vuadelle | Portfolio & Headless CMS

This repository contains the source code for the personal portfolio of Alexis Vuadelle, built on a modern split architecture featuring an **Astro** SSR frontend and a **Payload 3.0 / Next.js** headless CMS backend.

## 🏗 Architecture

The project is split into two distinct Node.js applications:

1. **/frontend**
   - **Framework:** Astro V6
   - **Styling:** Tailwind CSS V4
   - **Runtime:** Server-Side Rendering (SSR) via `@astrojs/node`
   - **Purpose:** Fast, highly-responsive frontend that dynamically fetches live data from the CMS.

2. **/cms**
   - **Framework:** Payload CMS 3.0 / Next.js
   - **Database:** PostgreSQL (`@payloadcms/db-postgres`)
   - **Purpose:** Centralized headless data administration for projects, profile links, and career information.

## 🚀 Deployment (O2Switch / cPanel / Phusion Passenger)

The project architecture has been specifically refactored to support seamless deployment into **o2switch's cPanel Node.js App** ecosystem, which relies on the strict Phusion Passenger routing module.

### Frontend Deployment (`/frontend`)
O2switch requires an explicit entry point file to initialize a server process natively. 
1. Open the cPanel **Setup Node.js App** utility.
2. Select your main domain (e.g., `alexis-vuadelle.com`).
3. Set the **Application startup file** to `server.js`.
4. Ensure the `.env` variables point to the live public URL of your CMS.
5. In SSH or the cPanel Terminal, navigate to the frontend directory and run `npm run build`.

### CMS Deployment (`/cms`)
The CMS acts as a discrete application on a secure subdomain.
1. Open the cPanel **Setup Node.js App** utility.
2. Create a deployment targeting your subdomain (e.g., `cms.alexis-vuadelle.com`).
3. Set the **Application startup file** to `server.js` (a custom Passenger intercept wrapper that pipes traffic to Next.js).
4. Add the `DATABASE_URI` environment variable, setting it firmly to your o2switch PostgreSQL connection URL (`postgresql://user:pass@localhost:5432/dbname`).
5. Add the `PAYLOAD_SECRET` environment variable (a random secure string).
6. In SSH, navigate to the CMS directory and run `npm run build`.

## 🛠 Local Development

When developing locally, we utilize **bun** for ultra-fast package management and execution.

1. Create local `.env` files supplying `DATABASE_URI`. 
   *(PostgreSQL is strictly required, ensure you have a local postgres instance or remote dev database available)* 
2. Enter the CMS: `cd cms && bun run dev`
3. Enter the Frontend: `cd frontend && bun run dev`
