# Aura Tune — Master Plan

## Product goal
Build an independent, free-to-use Android music player with a polished Spotify-inspired experience and useful features inspired by InterTune. Use original branding and assets. Do not copy Spotify proprietary assets or bypass paid access, DRM, advertisements, or service restrictions.

## Core principles
- ₹0 development budget; no paid AI API required for core features.
- No advertisements inside Aura Tune.
- Android-first; development through GitHub web editor and cloud builds.
- Kotlin + Jetpack Compose.
- AndroidX Media3 for playback, media session, background playback, notification and lock-screen controls.
- Small, maintainable single-module MVVM + Repository architecture; manual dependency injection initially.
- Use open-source dependencies only after checking their licences.
- Be honest about online-source reliability and provider terms.

## Music sources
1. Local audio files discovered with Android MediaStore.
2. Investigate a lawful YouTube Music-compatible online source similar to InterTune's approach. Verify the current implementation, source code, dependencies, licence, and service terms before choosing it. Do not assume unofficial endpoints are stable or authorised.
3. Investigate legal open-licensed/free music catalogues and their API limits.
4. Spotify playlist imports may use user-exported CSV metadata. A CSV does not contain the audio itself. Match tracks against sources the app is permitted to use and show uncertain matches for user confirmation.

## Roadmap
### Phase 0 — research and foundation
- Inspect InterTune's public source, licence, architecture, music-source implementation, and current maintenance status.
- Compare lawful music-source options and document limitations.
- Create a minimal Android project and verify cloud build.

### Phase 1 — working local player
- Scan and display local tracks.
- Browse tracks, albums, artists, and folders; search and sort.
- Play, pause, next, previous, queue, and basic playback state.
- Background playback via MediaSessionService.
- Notification and lock-screen controls; handle audio focus and interruptions.
- Gracefully skip unsupported or corrupted files.

### Phase 2 — online music foundation
- Add a source only after technical, licence, and terms review.
- Search, results, playback, loading/error states, and source attribution where required.
- Clearly communicate source limitations and avoid claiming guaranteed access to every Spotify track.

### Phase 3 — library and playlists
- Create/edit playlists and favourites.
- Listening history and recently played.
- Import Exportify/Spotify CSV metadata and match tracks with confidence checks.
- Queue management, shuffle, repeat, and backups.

### Phase 4 — InterTune-inspired features
- Lyrics from a permitted source.
- Sleep timer, playback speed, crossfade if supported, equalizer where device APIs permit.
- Themes, artwork, widgets, recommendations, radio, and listening statistics.

### Phase 5 — advanced integrations
- Evaluate Android Auto, casting, song recognition, headphone profiles, and additional recommendation features individually for feasibility, permissions, licences, and cost.

## Important constraints
- Full Spotify catalogue access is not available through a free unrestricted public API. Do not promise exact Spotify catalogue parity without a lawful source that actually provides it.
- Online services may change or restrict unofficial integrations; never promise permanent reliability.
- Downloads/offline caching must respect each provider's licence and terms. Local files are supported.
- Do not copy Spotify logos, proprietary artwork, or protected UI assets. Build an original Aura Tune identity.
- Do not add analytics or tracking by default.

## Definition of the first milestone
A cloud-built Android APK that scans local music and plays it with working background playback, notification controls, and a basic queue. Online music comes after the foundation builds successfully.

## Working method
- Implement one small step at a time.
- Keep changes easy to review in GitHub web editor.
- Build and test after each foundation step.
- Never claim a build or test passed unless its result was observed.
