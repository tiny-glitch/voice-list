# Voice Task List

A voice-first task list PWA. Tap the mic, speak your items, and they appear as a checklist. Simple, offline-capable, no accounts, no cloud sync.

**[Live Demo](https://voicenote-list.netlify.app)**

## Features

- Voice input via the Web Speech API
- Say multiple items at once — separated by "and" or commas
- Tap to check off items; clear completed in one tap
- Fully offline via service worker
- Data persists in localStorage — nothing leaves the device

## Tech

Vanilla HTML, CSS, and JavaScript. No frameworks, no build step, no dependencies. Five files total.

## Interesting problems solved

**Chrome Android fires multiple `onresult` events per utterance.** Without handling this, every spoken item appeared 2–3 times. Fixed with a `committedChunks` Set, revision prefix detection, and an 800ms hold timer on first results.

**Android's soft keyboard pushed the header offscreen.** Fixed with `overflow: hidden` on the body.

## Deployment

Hosted on Netlify. Requires HTTPS for microphone access via the Web Speech API.
