# Tut Dance / MOVE + PLAY

[Adult version](https://djmglotov-crypto.github.io/tut-dance/dance-adults.html?v=3) · [Kids version](https://djmglotov-crypto.github.io/tut-dance/dance-kids.html?v=3) · [Android test downloads](https://github.com/djmglotov-crypto/tut-dance/releases/tag/android-v0.3.0)

## Implementation
React web player with Canvas articulated rendering. Arms, elbows, wrists, knees, feet and torso move independently. Three authored keyframe combinations and three human motion-capture recordings (CMU Charleston 93_03, Salsa 60_01, playful dance 143_34). Source acknowledgments and usage terms: THIRD_PARTY.txt.

Audio sources: original procedural music library (100/118/128 BPM), local audio-file decoding and beat estimation, and microphone beat estimation. Audio stays on the device. Pause stops microphone tracks. Mirror, difficulty, theme, music and speech volumes, optional spoken movement cues, local activity/streak statistics, 15-second Canvas video recording, optional camera overlay and browser sharing are implemented.

## Source and builds
- `web-source.zip`: full React/Vite source, motion data and meaningful audio/animation checks (`node check.mjs`).
- `mobile-source.zip`: React Native/Expo source for iOS/Android, with the React dance engine and motion data bundled locally.
- Android workflow unpacks mobile source and creates separate MOVE and PLAY standalone APKs. These are test builds signed with the template development key, not Google Play releases.
- iOS source is included. A signed iPhone build requires macOS/Xcode and an Apple developer signing identity.

Web: unpack web-source.zip, enter web/, npm install, npm run build. Build destination is ../../outputs/tut-v3. Deployed HTML files inline the React bundle and motion records so the same player can run offline in the native app. After initial web loading, the service worker caches the site.

## Validation performed
Synthetic audio and pulse-stream 120 BPM analysis; independent wrist and foot trajectories in all base clips; finite coordinates and relative wrist motion in all three human motion clips; successful production web build. Browser checks: playing built-in music, manual clip selection, adult/kids switching, mobile layout, pausing and successful short video recording.

## Remaining specification work / acceptance limits
- Dedicated hip-hop and house clips are not included yet. The UI labels the actual recorded styles rather than relabeling them.
- Mocap playback speed adapts to BPM, but internal foot-contact/accent alignment needs choreographer annotation. A measured <=100ms synchronization guarantee is not established.
- 60 FPS, <=3-second cold start and power consumption have not been benchmarked across target phones.
- Camera overlay is not spatial AR/body tracking. Recording/sharing and file selection in the Android WebView require device validation.
- Activity counts demonstrated combinations, not verified user repetitions; there is no movement scoring.
- Spotify/Apple Music/VK streaming integration is future work. Store buttons explain that no store release exists yet.
- GDPR / Russian 152-FZ legal review is not complete. No compliance certification is claimed.
