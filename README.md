# sixteen-nein

Shell scripts for downloading a YouTube video, centre-cropping it to 4:3, and running it through `ntsc-rs-cli`.

## Requirements

This script is intended for macOS and Linux. It is a Bash script that depends on Unix shell tools, so Windows is not supported unless you run it through WSL or a similar Linux environment.

Install these commands before running the script:

- `yt-dlp`
- `ffmpeg`
- `ntsc-rs-cli`

### macOS

Using [Homebrew](https://brew.sh/):

```sh
brew install yt-dlp ffmpeg
```

Install `ntsc-rs-cli` from the [`ntsc-rs` releases page](https://github.com/valadaptive/ntsc-rs/releases).

### Linux

Install `yt-dlp` and `ffmpeg` with your distro's package manager. For example, on Debian or Ubuntu:

```sh
sudo apt update
sudo apt install yt-dlp ffmpeg
```

Install `ntsc-rs-cli` from the [`ntsc-rs` releases page](https://github.com/valadaptive/ntsc-rs/releases).

## Usage

```sh
bin/sixteen-nein <youtube-url> [output-file] [-- <ntsc-rs-cli args>]
```

Examples:

```sh
bin/sixteen-nein 'https://www.youtube.com/watch?v=dQw4w9WgXcQ'
bin/sixteen-nein 'https://youtu.be/dQw4w9WgXcQ' output.mp4 -- --scale 480 --interlace
```

The default output path is `sixteen-nein-output.mp4`.

To call it as `sixteen-nein`, add this repo's `bin` directory to your `PATH`:

```sh
export PATH="$PWD/bin:$PATH"
```
