audio-normalize
===============

Audio Normalization Script for Python/ffmpeg. I've only tested it with Python 2.7.
The script RMS-normalizes mp4 files to -26 dB RMS. It outputs mp4 files named as `normalized-<input>.mp4`. It can also do peak normalization.

Requirements
============

* Python 2.7.1 (https://www.python.org/downloads/release/python-2710/)
* Recent version of ffmpeg (download a [static build](http://ffmpeg.zeranoe.com/builds/) if you don't want to compile) in your `$PATH`
  * how to the $PATH in Windows => http://www.computerhope.com/issues/ch000549.htm

Usage
=====

Very simple:

    normalize.py -i <input-files> -v -l <level> -b <bitrate> -o <output-path>

    ex) normalize.py -i .\src\*.mp4 -v -l -20 -b 320 -o .
    it opens all of mp4 files in src folder and re-encode their audio to -20dB, 320kbps and then stores them named as .\normalized-<orignial file name>.mp4

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
