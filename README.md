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

# Full example
In steam command configuration:
```
STANDALONE_GAMESCOPE_TMP="/tmp/gamescope-session-1" /path/to/standalone-gamescope game %command%
```

# Arguments
## Gamescope arguments
### Prefixed with `--gs`
Gamescope arguments are prefixed with `--gs`, e.g.:
```bash
/path/to/standalone-gamescope game --gs--fullscreen %command%
```
### Removal prefixed with `---gs`
Gamescope arguments are prefixed with `---gs` in case default argument is to be removed, e.g.:
```bash
/path/to/standalone-gamescope game --gs--fullscreen %command%
```
### Arguments that take values
Arguments that take values are postfixed with `=`, e.g.:
```bash
/path/to/standalone-gamescope game ---gs--backend= --gs--hdr-itm-target-nits= 700  %command%
```
## Standalone gamescope arguments
Samre rules as for gamescope arguments, but prefixed with `--sgs/---sgs`, e.g.
```bash
/path/to/standalone-gamescope game ---sgs--force-dlss-rr ---sgs--force-dlss-fg ---sgs--force-dlss-profile-a= ---sgs--force-dlss-profile-b= %command%
```
## Default argument values
```bash
  --gs--nested-width= 2560 --gs--nested-height= 1440
  --gs--output-width= 2560 --gs--output-height= 1440
  --gs--backend= wayland
  --gs--fullscreen
  --gs--force-grab-cursor
  --gs--hdr-enabled
  --gs--adaptive-sync
  --gs--hdr-itm-enable
  --gs--hdr-itm-target-nits= 400
  --gs--hdr-itm-sdr-nits= 100
  --gs--hdr-sdr-content-nits= 400
  ---sgs--force-dlss-latest-version
  --sgs--force-dlss-rr
  --sgs--force-dlss-fg
  ---sgs--force-dlss-indicator
  --sgs--force-dlss-profile-a= 0xffffff
  --sgs--force-dlss-profile-b= 0xffffff
```
