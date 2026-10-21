# Riff to Tab

Turn a recording of a guitar, bass, or piano into tablature (or notes on a staff for piano), right in the browser.
Everything is one self-contained page, `index.html`: open it in a browser or serve it from any static host
(Netlify, GitHub Pages and so on). Recordings are analyzed on your device and are never uploaded.

## Features

- **Upload or record:** load an audio file, or record from the microphone (Record works when the page is opened
  directly, for example from Netlify or GitHub Pages).
- **Pitch tracking:** pYIN-style tracking with spectral-flux onsets, tuned on real guitar recordings, with
  string-noise filtering and octave-error correction.
- **Guitar techniques:** detects bends (`^`), vibrato (`~`), hammer-ons (`h`), pull-offs (`p`) and slides (`/`, `\`).
- **Two notes at once:** double stops and power chords. With **Notes at once → Up to two (chord model)**, chords come
  from Spotify's open-source [Basic Pitch](https://github.com/spotify/basic-pitch-ts) model, layered on top of the
  built-in single-note detection. Choose **One** for single-note lines.
- **Fingering:** playable fret positions, with three styles (fewest hand moves, prefer fretted notes, stay on one
  string). Chords keep one shape moving along the same strings, and single notes stay inside the shape.
- **Tunings:** many guitar and bass tunings, custom tunings, capo, and 7- and 8-string guitars.
- **Rhythm:** estimates the tempo and time signature and draws bar lines. Common, odd and custom time signatures,
  for very complex meters too.
- **Playback:** play the recording or the tab, with a moving playhead; tap anywhere to play from that point.
- **Note editor:** fix pitch and position, delete or add notes, change how a note was played, and undo.
- **Instruments:** guitar, bass, and piano (grand staff).

## Using it

Open `index.html`, choose an instrument and tuning, then load a recording or press Record. For the best results,
record one or two notes at a time, with a clean tone and no backing track.

The chord model is built into the page. The first time it's needed, the page also loads TensorFlow.js from
cdn.jsdelivr.net, so that step needs an internet connection. If the model can't run, the page falls back to its
built-in two-note search.

## Credits and licenses

- **Basic Pitch** © Spotify AB, licensed under the [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0).
  Its inference and note-extraction code and its trained model weights are bundled in `index.html`.
  Source: <https://github.com/spotify/basic-pitch-ts>
- **TensorFlow.js** © Google LLC, licensed under the Apache License 2.0. It is loaded from cdn.jsdelivr.net at runtime.
