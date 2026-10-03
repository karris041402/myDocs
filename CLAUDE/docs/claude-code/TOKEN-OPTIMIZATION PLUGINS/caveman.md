# Caveman Setup for Claude Code

Caveman has two separate components:

1. Caveman Plugin
2. Caveman CLI / Proxy

They solve different token-usage problems.

---

## 1. Caveman Plugin

### Purpose

The Caveman plugin changes how Claude responds.

Main effect:

- Shorter responses
- Less filler
- More direct explanations
- Keeps important code, commands, paths, and errors

Example:

Without Caveman:

```text
I checked the component and it appears that the issue is caused by the object being recreated every time the component renders...
```
