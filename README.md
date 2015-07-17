audio-normalize
===============

Audio Normalization Script for Python/ffmpeg. I've only tested it with Python 2.6, not Python 3.
The script RMS-normalizes media files (video, audio) to -26 dB RMS. It outputs PCM WAV files named as `normalized-<input>.wav`. It can also do peak normalization.

Requirements
============

* Python
* Recent version of ffmpeg (download a [static build](http://ffmpeg.org/download.html) if you don't want to compile) in your `$PATH`

Usage
=====

Very simple:

    ./normalize.py -i <input-file> -v

Options
=======

- `-f`, `--force`                Force overwriting existing files
- `-l  LEVEL`, `--level LEVEL`   level to normalize to (default: -26 dB)
- `-p PREFIX`, `--prefix PREFIX` Normalized file prefix (default: "normalized")
- `-m`, `--max`                  Normalize to the maximum (peak) volume instead of RMS
- `-v`, `--verbose`              Enable verbose output
- `-n`, `--dry-run`              Show what would be done, do not convert
- `-b`, `--bitrate`              Audio bitrate in Kilo, default: 320
- `-o`, `--output_path`          Output path (default: ./)

