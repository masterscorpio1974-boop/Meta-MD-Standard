# Meta.md Standard

### The Problem
AIs lose memory in SAME chat after 2-4 hours idle. I lost 48h of work building APK in Termux. Same happens in Meta AI, Copilot, Gemini.

Storing full 50k tokens is expensive.

### The Solution: Meta.md
One small file in project root that AI reads every time.

1. User creates Meta.md
2. AI reads at start
3. AI updates with important facts
4. If AI forgets, it reloads Meta.md

### Example
### Why better
- 99% cheaper
- Persistent
- User can edit
- Universal for all AIs

Proposed by scorpiomaster066-art
