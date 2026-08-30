# Changes from ffmpeg-webCLI (original)

This file documents modifications made to the original ffmpeg-webCLI codebase, as required by GPL-3.0.

## Unreleased
- Project renamed to PixelPress; identity and README updated.

## Phase 6-9
- Video Analyzer: Media Info panel extended with real ffprobe deep-scan results (Video/Audio/Container), labeled by source; unavailable fields (e.g. GOP) shown honestly instead of guessed. Two-path scan: real ffprobe JSON first, falls back to parsing plain-text `ffmpeg -i` output when ffprobe isn't available in the loaded core build.
- FFmpeg Command Generator: interactive builder (codec, preset, CRF, resolution, audio codec/bitrate, output format) with live command preview, Copy Command, and Run Command.
- Bitrate/Quality Calculator: standalone equal-allocation calculator across N channels, budget entered as kb/s or as total size (MB) + duration.
