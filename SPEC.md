# Meta.md Standard - Specification v1.0
Author: scorpiomaster066-art
Date: 2026-05-13
Status: Proposal
Related: cli/cli#13920, termux/termux-app, microsoft/vscode

## 1. Overview
A single persistent memory file for AI assistants to survive chat idle/resets.

## 2. File Spec
- Name: Meta.md (or.meta.md alternative)
- Location: Project root /Meta.md
- Format: Markdown, human-readable and editable
- Size: < 2KB recommended, max 50 lines

## 3. Required Fields
- Project: [name]
- Owner: [github username]
- Stack: [e.g., Termux, Android, Gradle 8.5, JDK 17]
- Issue: [related issue link]
- Rule: Never ask same info twice. If confused, reload this file. Always warn if build will fail and why.

Example:
# Project: GestorMasterS-app
- Owner: scorpiomaster066-art
- Stack: Termux, Android, Gradle 8.5, JDK 17
- Issue: cli/cli#13920

## 4. AI Behavior Rules
1. MUST read Meta.md at start of every session.
2. MUST update it when learning critical project facts.
3. MUST reload it if context is lost after 2-4h idle.
4. MUST NOT ask for info already in Meta.md.
5. MUST warn before any destructive/failing build.

## 5. Why Better than 50k tokens
- 99% cheaper (2KB vs 50k tokens)
- Persistent across sessions, devices, AIs
- User owns and edits it
- Universal: Works with Meta AI, Copilot, Gemini, Claude, ChatGPT

## 6. Future: Self-Healing Telemetry (v2)
- Detect -> Self-Fix -> Report with Permission -> Human Guard
- See README.md for full proposal.

License: MIT
