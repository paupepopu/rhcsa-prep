# Quick Tips

Short, one-off notes and best practices picked up during the course that
don't yet belong to a specific exam objective folder. Entries here can be
folded into the relevant topic's `notes.md` later once it's clear where
they fit.

---

**2026-08-18 — Avoid Logging In as Root Directly**
Best practice is to avoid using the root account for day-to-day login;
use a regular user with `sudo` instead so privileged actions are tied to
an identifiable user and logged. Root itself isn't removed — just kept
out of routine use. Related to [`09-users-and-groups`](./09-users-and-groups/notes.md)
and [`10-security`](./10-security/notes.md).
