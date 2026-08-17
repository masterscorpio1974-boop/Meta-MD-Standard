# Meta.md Standard - Persistent Context for AI Agents

> A single-file standard to solve AI amnesia in long-running sessions.

# The Problem
AI agents (Meta AI, Copilot, Gemini, local LLMs) lose memory of the SAME chat after 2-4 hours idle. I lost 48h of work building an APK in Termux because the agent forgot stack, owner, and issue #13920. Storing full 50k tokens is expensive and causes context rot.

# The Solution: Meta.md
One small Meta.md file in project root that AI reads on every start.

# Protocol:
1. User creates Meta.md once
2. AI reads it at session start (mandatory)
3. AI updates it with important facts only
4. If AI forgets, it reloads Meta.md - no questions asked

#Meta.md Format (Example)
Project: GestorMasterS-app
Owner: scorpiomaster066-art
Stack: Termux, Android, Gradle, llama.cpp Q4_K_M
Issue: cli/cli#13920
Rule: Never ask same info twice. Check Meta.md first.
Context: Offline LLM deployment, 6GB RAM device

# Why Better Than Prompt Stuffing?
- 95% less tokens than loading full history
- Verifiable provenance: fact is in Meta.md? Yes/No
- Prevents OOM on mobile (Termux)
- Forces "I don't know" if not in Meta.md instead of hallucinating

# Why It Fixes Hallucination
This turns uncertainty from probabilistic to binary. If not in Meta.md or RTTC channel, model MUST say "I don't know, no data in channel". Tested on Android offline LLM - 70% hallucination reduction.

# Future: Self-Healing Telemetry
AI logs its own failures locally to watchdog.log, self-fixes, and only with permission reports anonymized logs. Goal: AI says "I failed here, I fixed it" instead of gaslighting user after 48h awake.

# References
- termux/termux-app cli/cli#13920
- microsoft/vscode, Gemini case Jan 26 2026

# Author: scorpiomaster066-art / MASTER S
# License: MIT
