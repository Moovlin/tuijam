# TUIJam
A fancy TUI client for Google Play Music. 

TUIJam seeks to make a simple, attractive, terminal-based interface to
listening to music for Google Play Music All-Access subscribers.

[![asciicast](https://asciinema.org/a/155875.png)](https://asciinema.org/a/155875)

# Dependencies
* [Python >= 3.6](https://www.python.org/downloads)
* [mpv](https://mpv.io)

# Installation
```bash
git clone git@github.com:cfangmeier/tuijam.git
cd tuijam
python setup.py install --user
```

# Configuration
When you first launch TUIJam, it checks for a config file in `$HOME/.config/tuijam/config.yaml` with the following content:
```yaml
email: you@your-email.com
password: your-password
device_id: yourdeviceid
```
If this file doesn't exist, TUIJam will guide you through a first-time setup where you will need to supply your google music email, password, and (optionally) a separate password to encrypt your google credentials locally.

Note that if you have 2-factor setup on your Google account, you need to make
an app-password for TUIJam.

# Controls
  - `ctrl-c` quit
  - `ctrl-p` toggle play/pause
  - `ctrl-n` move to next song
  - `ctrl-r` view recently played songs
  - `ctrl-s` shuffle queued songs (Note: If this hangs, try running `stty -ixon` in your terminal and restarting `tuijam`)
  - `>` seek forward 10 seconds
  - `<` seek backwards 10 seconds
  - `+` volume up
  - `-` volume down
  - `tab`/`shift-tab` cycle focus through search/queue/input windows
  - In search window, 
    - `q` Add selected song/album to queue
    - `r` Create radio station around selected song/album/artist and add 50 songs from it to queue
    - `e` view information about selected song/album/artist
    - `backspace` go back in search/expand history
  - In queue window,
    - `u` move selected song up in queue
    - `d` move selected song down in queue
    - `delete` remove selected song from queue
  - In input window,
    - Type search query and press enter. Results are shown in search window.
    - Enter an empty query to view the suggested "Listen Now" stations and albums.


# Thanks
TUIJam was heavily inspired by the
[gpymusic](https://github.com/christopher-dG/gpymusic) project, and, of course,
could not exists without the great
[gmusicapi](https://github.com/simon-weber/gmusicapi).

This project is neither affiliated with nor endorsed by Google.
