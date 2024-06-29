# Standalone Gamescope
This project is intended to run nested gamescope off-process.

# Requirements
`ruby`

Either from OS package manager: `ruby-json`, `ruby-fileutils`
Or via gem install `gem install json`, `gem install fileutils`

# Running
to execute as server process if you wish to manually control it's startup
___
```bash
/path/to/standalone-gamescope start
```

to execute a game/program and automatically start server process if it is not started:
___
```bash
/path/to/standalone-gamescope game /path/to/game/executable
```

to run a e.g. steam game
___
```bash
/path/to/standalone-gamescope game %command%
```

# ENV variables
`STANDALONE_GAMESCOPE_TMP` - path for tempfiles/pidfiles. Default - directory of script

`GAMESCOPE_ARGS` - gamescope arguments. Default - `-w 2560 -h 1440 -W 2560 -H 1440 --fullscreen --hdr-enabled --nested-refresh 165 --hdr-sdr-content-nits 100`

# Full example
In steam command configuration:
```
STANDALONE_GAMESCOPE_TMP="/tmp/gamescope-session-1" GAMESCOPE_ARGS="-w 2560 -h 1440 -W 1920 -H 1080 --fullscreen" /path/to/standalone-gamescope game %command%
```
