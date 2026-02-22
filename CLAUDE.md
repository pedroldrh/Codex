# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Structure

This is a personal workspace directory containing multiple projects and files:

- `index.html` - Professional portfolio website with dark mode toggle
- `package.json` - Node.js dependencies (express, cors, sqlite3)
- `CascadeProjects/` - Cascade-related projects
- `PycharmProjects/` - Python projects
- `experience-exchange-redesign/` - Experience exchange redesign project
- `lignum/` - Lignum project
- `voice_control/` - Voice control project
- `Downloads/` - Downloaded files including Python scripts and exercises

## Working in This Environment

This is a home directory workspace, not a single cohesive project. When working here:

1. **Identify the specific project** the user is referring to before making changes
2. **Navigate to the appropriate subdirectory** (CascadeProjects, PycharmProjects, etc.) for project-specific work
3. **Avoid making changes at the root level** unless explicitly requested

## Portfolio Website (index.html)

The root-level `index.html` is a self-contained single-page portfolio website featuring:
- Responsive design with mobile menu
- Dark/light theme toggle (persisted in localStorage)
- Sections: Hero, About, Skills, Projects, Experience, Contact
- Contact form with validation
- Smooth scrolling navigation
- Intersection Observer animations

No build process required - open directly in a browser.

## Node.js Setup

Basic Node.js dependencies are available:
```bash
npm install  # Install express, cors, sqlite3
```

No specific build, test, or run commands defined in package.json.

## Learning Log

When making a mistake or encountering something unexpected, always add the lesson here so it's not repeated.

### WLU Forecaster
- **Always grep for all usages** before removing a prop/interface field. When removing `avatarUrl` from `UserAvatar`, I missed `comment-section.tsx` because it wasn't listed in the plan. Always run a codebase-wide search (e.g. `Grep`) for the prop name before removing it.
- **Never hardcode secrets in scripts**. The seed script (`scripts/seed-users.mjs`) was committed with the Supabase service role key hardcoded, triggering a GitHub secret scanning alert. Always read credentials from `.env` via `readFileSync` or `dotenv`, never inline them.
