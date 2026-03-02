# On The Spot

A real-time meeting copilot for macOS. Transcribes conversations, retrieves context from your local knowledge base, and generates talking-point suggestions as you talk.

Built with SwiftUI, using Apple's on-device Speech framework for transcription and OpenRouter for LLM-powered suggestions.

## Features

- On-device speech-to-text via Apple Speech framework (no cloud transcription)
- Dual audio capture: microphone (you) + system audio (them)
- Knowledge base indexing from local `.md` and `.txt` files
- LLM-powered suggestion engine via OpenRouter (any model)
- Compact, partially transparent window designed to sit alongside your call
- Floating overlay mode (Cmd+Shift+O) for screen-share-safe suggestions
- Input device selection for choosing your microphone
- Audio level visualization showing live mic activity
- Session logging to local JSONL files

## Requirements

- macOS 26+ (Apple Silicon)
- Xcode / Swift toolchain

## Build

```bash
./scripts/build_swift_app.sh
```

This builds a signed `.app` bundle and installs it to `/Applications/On The Spot.app`.

Optional env vars for code signing and notarization:
- `CODESIGN_IDENTITY`
- `APPLE_ID`
- `APPLE_TEAM_ID`
- `APPLE_APP_PASSWORD`

## Setup

1. Launch the app
2. Open Settings (Cmd+,)
3. Set your OpenRouter API key
4. Choose an LLM model (e.g. `google/gemini-3-flash-preview`)
5. Select your microphone input device
6. Optionally choose a knowledge base folder containing `.md`/`.txt` files

## Usage

- Click **Idle** in the bottom bar to start a session (switches to **Live**)
- Audio level bars show mic activity in real time
- Suggestions appear automatically when the other person speaks about topics in your KB
- Expand the **Transcript** section to see the live conversation
- **Cmd+Shift+O** toggles the floating overlay (invisible to screen sharing)
- **Esc** hides the overlay

## Build DMG

```bash
./scripts/make_dmg.sh
```
