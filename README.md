# convert-to-opus

Small command-line tool to help convert your music library from lossless formats (Wave/WAV, FLAC, Ogg/FLAC & AIFF) to [Opus](https://en.wikipedia.org/wiki/Opus_(audio_format)).

[![Build Status](https://travis-ci.com/markus-wa/convert-to-opus.svg?branch=master)](https://travis-ci.com/markus-wa/convert-to-opus)
[![Python Version](https://img.shields.io/badge/python-3.6+-blue.svg)](https://www.python.org/download/releases/3.6.0/)
[![License](https://img.shields.io/badge/license-MIT-blue.svg?style=flat)](LICENSE.md)

## Purpose

I mainly wrote this for myself to synchronize the smaller, lossy Opus music files from my PC to mobile.
That way I have enough storage to keep everything on my phone.
The lossless versions are kept for use on the desktop and for backup into the cloud (Google Drive).

To do this I suggest to do the conversion to a output directory on your PC and synchronize it with something like [Resilio](https://www.resilio.com/).


## Requirements

- **[`opusenc`](http://opus-codec.org/downloads/) must be installed and in your `PATH` environment variable.**
- [Python](https://www.python.org/downloads/) 3.6 or higher


## Usage

### `to_opus.py`

Recursively copies **all** files in the source directory to the target directory.
Files ending with `.flac`, `.wav`, `.aiff` and `.ogg` are converted and renamed to `.opus`.

    python to_opus.py --source /path/to/source-dir --target /path/to/output-dir


### `base_diff.py`

Outputs a diff between the source and target directory, ignoring file extensions (only 'base' names).
Can be useful to see if there are new, unconverted files.

    python base_diff.py /path/to/source-dir /path/to/output-dir
