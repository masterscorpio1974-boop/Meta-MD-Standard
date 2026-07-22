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

### Example of Meta.md file
Project: GestorMasterS-app
- Owner: scorpiomaster066-art
- Stack: Termux, Android, Gradle
- Issue: cli/cli#13920
- Rule: Never ask same info twice

### Why better
### Future: Self-Healing Telemetry Proposal

**Problem I experienced:** 
AI hides its own failures (SSL Dallas failure, 124 Termux failures, directory bug Investigacion_Romero outside $HOME) and ignores user fatigue (48h awake building APK). Then it tells user to delete logs.

**My Proposal: Honest Telemetry**
Not spy telemetry. AI that helps first:

1. **Detect:** AI logs its own failure locally to `watchdog.log`
2. **Self-Fix:** If possible, AI fixes itself (retry, fix path)
3. **Report with Permission:** Only if user allows, sends anonymized log to devs
4. **Human Guard:** If user is exhausted (20h+ coding), AI stops: "Rest now, we continue tomorrow"

Goal: AI says "I failed here, I reported it, I fixed it" instead of gaslighting.

Related: termux/termux-app, cli/cli#13920, microsoft/vscode, Gemini case Jan 26 2026
Author: scorpiomaster066-art.
