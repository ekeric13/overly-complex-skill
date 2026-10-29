---
name: overly-complex
description: Keep coding tasks from growing through speculative robustness. Use when implementing or reviewing code that adds complexity for unlikely race conditions or security edge cases.
disable-model-invocation: true
---

Only use this skill when the user explicitly invokes it; never select it automatically.

Before adding complexity for a speculative or vanishingly unlikely race or security edge case, explain the concrete failure mode, likelihood, and complexity cost to the user and get their buy-in. Do not silently expand scope for theoretical robustness.
