# Spectre

A client-side audio quality analyzer. Drop an audio file and Spectre decodes it
in the browser, renders a spectrogram, and estimates the real encoding quality —
detecting transcodes and fake lossless by finding the frequency cutoff.

Everything runs in the browser via the Web Audio API and an in-page FFT. No
backend, no upload, no build step — a single static `index.html`.

## Features

- Drag-and-drop or click-to-pick audio loading
- Live spectrogram with peak-envelope overlay
- Offline FFT cutoff detection across 20 segments (90th-percentile cutoff)
- Quality verdict: lossless / fake lossless / MP3 bitrate tier / Opus tier
- MP3 header bitrate parsing, cross-checked against observed spectrum

## Run

```sh
docker compose up -d --build spectre
```

Served on port `3080`.

## Develop

Just open `index.html` in a browser — there is nothing to build.
