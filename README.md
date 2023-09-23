# Forked README

This fork is to update the script to work with the `REWRITE` branch of [DownOnSpot](https://github.com/oSumAtrIX/DownOnSpot).

Tested with DownOnSpot commits `eed7fda` and `01ca2df`. On __WINDOWS__ but it is a simple Python script so it should work on other operating systems.

This is not at all production level code but it should work in the majority of cases.

## Install

Make sure the required Python libraries are installed (a virtual environment is recommended), see `requirements.txt`.

Compile the `REWRITE` branch of [DownOnSpot](https://github.com/oSumAtrIX/DownOnSpot).

## Config

Modify the `.env` and `config.json` files.

`.env` requires the Spotify tokens (see [DownOnSpot](https://github.com/oSumAtrIX/DownOnSpot) for help on how to get them).

In `config.json` specify the temporary location for DownOnSpot files, the location of the DownOnSpot executable, the folder where the playlists will be downloaded.
Also change the region with yours and of course add the playlist URLs you want to download.

> The `extensions_to_scan` parameter should not be changed as the rewrite is only able to download OGG files (for now).

## Usage

Once properly onfigured, simply launch the script with: `python script.py`

# Original README

A python script for keeping Spotify playlists in sync with local music library.

The script fetches data for all tracks of a Spotify playlist (using Spotipy) then do it's magic and find tracks that needs to be downloaded and then saves them locally (using DownOnSpot) and keep them in separate folders based on playlist name. It will filter out any tracks that have already been downloaded, are unavailable or are uploaded.

## Features

- Keeps Spotify playlists in sync with local folders organized by playlist names
- Handles tracks with same title, or artist, or even both and rename files accordingly
- Handles duplicate tracks that have been added twice to the same playlist
- Updates file modification date to match with date when track was added to the playlist

## Important

- This script relies heavily on DownOnSpot tool for saving tracks locally, so you are required to have DownOnSpot successfully installed on your computer.

## Notes

- All tracks from a playlist are downloaded in a single folder (no subfolder for artist or album)
- Script's download folder needs to be same as configured in DownOnSpot's config
- Script will empty the specified download folder before running so don't put anything important there \*
- Any extra tracks present in playlist folder locally that are not present in Spotify playlist will be removed
- Uploaded tracks will be ignored because they can't be downloaded by DownOnSpot
- Metadata libraries like music-tag and Mutagen have only been tested with MP3 files
- Notes marked as \* means they are temporary restrictions and will be fixed soon

## Usage

- Fill out all settings in `config.json`
- Fill `CLIENT_ID` and `CLIENT_SECRET` in `.env` file for Spotipy library
- Open cmd and change it's directory to the script's folder:

  `cd /d unify-script-for-spotify`

- Run the script:

  `py script.py`

## Upcoming features

- Download user's Liked Songs library
- Download unavailable tracks by changing region for those tracks

## Other facts

- I'm not good at documenting stuff so apologies if something is not clear
- I create scripts for fun that would help me automating my stuff and occasionally I share them on GitHub :)

As always, if you have any features in mind, or something is not working, or you're stuck, let me know in Issues section, I will help you out! :smile:
