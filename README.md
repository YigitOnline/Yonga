# Yonga 1.0.1 — A Personal AI Agent for Mac

Yonga is a desktop AI agent that carries out natural-language tasks on your Mac. It uses the Gemini, ChatGPT, and Claude websites through Chrome, so no API key is required. Provider account limits and subscription requirements still apply.

## What's new in 1.0.1

- The app is now called **Yonga**, with the original icon preserved.
- **Remote Agent** stays fixed in the heading while **Gemini → ChatGPT → Claude → Yonga** are typed and erased, letter by letter, in a repeating terminal-style animation.
- The heading keeps a stable layout. Users who prefer reduced motion see a static Yonga label.
- The existing data folder and internal app identifier are preserved for compatibility with saved sessions and records.

The animated names are branding; they do not indicate or change the active provider.

## What can Yonga do?

- Read, create, and edit files and folders.
- Run shell commands and AppleScript.
- Analyze screenshots and control apps with mouse and keyboard actions.
- Send supplied files and images to an AI provider for analysis.
- Present plans for multi-step work and check action results.
- Attempt to continue with the next signed-in provider if the current provider fails, transferring the task context.

Describe your task in the chat window. For example:

> “Inspect the files in my workspace and explain the project structure.”
>
> “Create a simple to-do list web app.”

## Features

- **One Mac app containing Intel and Apple Silicon components.**
- A dedicated window for chat, plans, and action approvals.
- Sign-in buttons for Gemini, ChatGPT, and Claude.
- Bundled Python, Playwright, and cliclick; no separate Python or Homebrew installation required.
- A separate Chrome profile for persistent account sessions.
- Task records, an audit log, and file backups.
- An emergency stop button and optional automatic approval for write actions.

## Requirements

- **macOS 13.5 or later**
- **Google Chrome**
- An internet connection
- An account with at least one supported provider: Gemini, ChatGPT, or Claude

## Installation

1. Download `Yonga-Mac-Universal.zip` from this release's **Assets** section.
2. Extract the ZIP and move `Yonga.app` to **Applications**.
3. Double-click the app.
4. Click **Gemini giriş**, **ChatGPT giriş**, or **Claude giriş** in the top bar. These are the sign-in buttons; the current interface is in Turkish.
5. Sign in yourself in the Chrome window. The agent starts after sign-in is detected; click **Başlat** (Start) if necessary.
6. Type a task into the chat box and press Enter.

Mouse and keyboard control require **Accessibility** permission. Screenshots require **Screen Recording**, and application control requires **Automation**. Full Disk Access is only needed for protected data. Grant the relevant permissions in macOS **Privacy & Security**, then restart the app.

The package is **ad hoc signed**. It does not have an Apple Developer ID signature or Apple notarization. If macOS blocks the first launch, verify the download source before using the available opening option in **System Settings → Privacy & Security**.

## Control and privacy

Read actions run automatically. Write actions require approval by default; enabling **Automatic approval** allows write actions without individual approval. Destructive actions—including deletion, moving, closing, and risky operations involving personal-data apps—always require user approval.

The file write and patch tools create backups. The file deletion tool uses Trash rather than permanent deletion. Shell commands and application actions can have different effects, so read each approval card before accepting it.

Yonga runs on your Mac, but task messages, files supplied for analysis, and captured screenshots are sent to the selected AI provider. Close sensitive content before screen-based tasks. Your clipboard may change during message transfer.

The distribution contains no personal Chrome sessions or previous task records. You sign in to your accounts yourself.

## Where is data stored?

- Default task workspace: `~/AgentWorkspace`
- Chrome profile, task records, and backups: `~/Library/Application Support/GRT`

The **Kayıtlar** (Records) button opens the data folder. The legacy `GRT` folder name is intentional and preserves compatibility. Do not share this folder: it may contain account sessions and task content.

## Validation and known limitations

- All **328 existing project tests** passed using the bundled Intel Python runtime.
- The Intel Playwright driver, local chat flow, token authentication, file uploads, and backend termination were checked.
- Intel and arm64 component architectures, ZIP integrity, and the extracted package's code signature were verified.
- The heading's name sequence, letter-by-letter typing and erasing, and reduced-motion behavior were checked.
- **Execution on a physical Apple Silicon Mac has not been tested.**
- **End-to-end launch of the native app window has not been verified**, because the development session restricted desktop application access.
- **A live task with a real provider through this new package has not been tested separately.** Local chat checks used an offline test provider.
- Provider website changes may require updates to interface selectors.
- Only one task runs at a time. Screen-coordinate control depends on window placement and can make mistakes.

This is an early release. Start with a simple read-only task to check your account connection and permissions.
