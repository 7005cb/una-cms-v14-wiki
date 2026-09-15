# UNA CMS V14 – Agent Knowledge Base

This repo is intended as a structured knowledge base for AI coding agents working with UNA CMS V14.

## Repo structure and entry point

- All wiki content lives under `wiki-name/`.
- Each topic is a folder with a single `Skills.md` file:
  - Example: `wiki-name/Home/Skills.md`, `wiki-name/Architecture/Skills.md`, `wiki-name/Code-Convention/Skills.md`.
- The logical “home page” for the wiki is:
  - `wiki-name/Home/Skills.md`

When using this repo as a knowledge source, treat `wiki-name/Home/Skills.md` as the starting point, then follow links to other `*/Skills.md` files.

## How agents should use this repo

When generating, reviewing, or refactoring UNA CMS code:

1. **Always check conventions first**
   - Coding standards: `wiki-name/Code-Convention/Skills.md`
   - Code quality rules: `wiki-name/Code-Quality/Skills.md`
   - Directory/folder layout: `wiki-name/Directories-structure/Skills.md`

2. **Follow architecture and app model**
   - Architecture overview: `wiki-name/Architecture/Skills.md`
   - Core apps: `wiki-name/Core-Apps/Skills.md`
   - System apps: `wiki-name/System-Apps/Skills.md`
   - Studio & builders: `wiki-name/Studio/Skills.md`, `wiki-name/Forms-Builder/Skills.md`, `wiki-name/Pages-Builder/Skills.md`, `wiki-name/Navigation-Builder/Skills.md`, `wiki-name/Permissions-Builder/Skills.md`

3. **Use dev guides for concrete patterns**
   - API: `wiki-name/Dev-API/Skills.md`
   - Forms: `wiki-name/Dev-Forms/Skills.md`
   - Grids: `wiki-name/Dev-Grids/Skills.md`
   - Pages: `wiki-name/Dev-Pages/Skills.md`
   - Pagination: `wiki-name/Dev-Pagination/Skills.md`
   - Storage: `wiki-name/Dev-Storage/Skills.md`
   - Uploaders: `wiki-name/Dev-Uploaders/Skills.md`

4. **Respect data & security constraints**
   - DB & personal data: `wiki-name/List-of-personal-data-and-sensitive-content-in-the-DB/Skills.md`
   - Payments: `wiki-name/Payments/Skills.md`
   - Permissions: `wiki-name/Permissions-Builder/Skills.md`

## Expectations for generated code

All generated UNA CMS code must:

- Follow naming, file, and folder conventions in `Code-Convention` and `Directories-structure`.
- Use the UNA app/module structure described in `Architecture`, `Core-Apps`, and `System-Apps`.
- Implement forms, grids, pages, and APIs according to the corresponding `Dev-*` skills.
- Be consistent with existing patterns in the UNA CMS V14 codebase.

If a requested task conflicts with these docs, prefer the conventions and architecture defined here and explain the deviation.
