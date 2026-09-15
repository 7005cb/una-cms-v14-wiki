# UNA CMS V14 – Architecture

This document describes the high-level architecture of UNA CMS V14.

## Quick rules for AI coding agents

When generating or modifying UNA CMS code:

- Treat **Core**, **Objects**, **Plugins**, and **Modules** as described below; do not mix their responsibilities.
- Follow the **MVC** pattern:
  - **Model (M)** – `*Db` classes for data access.
  - **Controller (C)** – `*Module` classes for business logic.
  - **View (V)** – `*Templ*` classes and files in `/template/`.
- Keep modules **independent** and **removable**; do not hard-code cross-module dependencies.
- Use system folders (`/cache/`, `/tmp/`, `/logs/`, `/storage/`) instead of module-local storage where specified.

If a design decision conflicts with this architecture, prefer the structure described here and explain the deviation.

---

**Core** consists of some basic files like utilities, base classes, interfaces.  
**Objects** are helper classes which provide high level interface for some functionality.  
**Plugins** are 3rd-party libraries.  
**Modules** are separate, complete, independent piece of code which can be added or removed at any time.

![UNA Architecture Diagram](images/architecture-diagram.png)

**M** - Model, `*Db` classes  

**C** - Controller, `*Module` classes  

**V** - View, `*Templ*` classes and files in `/template/` folder.
