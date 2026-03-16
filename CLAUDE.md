# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This repository contains a personal [beets](https://beets.io/) music library manager configuration. Beets is a Python-based music tagger and organizer.

## Setup

```bash
pip install beets
pip install python3-discogs-client pylast
cp config.yaml ~/.config/beets/
```

## Common beets commands

```bash
beet import /Music          # import music folder
beet ls                     # list library
beet modify <query>         # modify tags
beet mbsync                 # sync metadata from MusicBrainz
beet fetchart               # fetch album art
beet duplicates             # find duplicates
beet missing                # find missing tracks
```

## Configuration structure

`config.yaml` is the single configuration file. Key sections:

- **import**: move (not copy) files to `~/music`, auto-tag with strong match threshold of 90% (`strong_rec_thresh: 0.1`)
- **paths**: music organized as `Artist/Album/track - Artist - Title`, with separate layouts for singletons and compilations
- **plugins**: discogs, lyrics, fetchart, embedart, lastgenre, scrub, mbsync, missing, duplicates
- **match**: distance weights tuned to favor `album_id` and `track_id` matches from MusicBrainz

## Plugin dependencies

- `python3-discogs-client` — required for the `discogs` plugin
- `pylast` — required for the `lastgenre` plugin (Last.fm)
