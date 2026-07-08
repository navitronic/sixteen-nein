# sixteen-nein

We all know that the look of skateboard videos peaked with VHS and the 4:3 aspect ratio. So, let's revisit that magic.

This repository contains a shell script for combining the process of downloading a YouTube video, centre-cropping it to 4:3, and running it through `ntsc-rs-cli` for a VHS look.

[toc]

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

> _Important:_ This isn't a quick process, running the script takes a while, even on a powerful machine.

```sh
bin/sixteen-nein [--size <height>] <youtube-url> [output-file] [-- <ntsc-rs-cli args>]
```

Use `--size` to choose the maximum YouTube video height to download, such as `480p`, `720p`, or `1080p`.

Examples:

```sh
bin/sixteen-nein 'https://www.youtube.com/watch?v=dQw4w9WgXcQ'
bin/sixteen-nein --size 720p 'https://youtu.be/dQw4w9WgXcQ' output.mp4
bin/sixteen-nein 'https://youtu.be/dQw4w9WgXcQ' output.mp4 -- --scale 480 --interlace
```

The default output path is `sixteen-nein-output.mp4`.

To call it as `sixteen-nein`, add this repo's `bin` directory to your `PATH`:

```sh
export PATH="$PWD/bin:$PATH"
```

## Questions you'd probably ask if you cared about this

### Something is broken or not working

Open an issue, describe the problem and I'll try to help.

### Why?

I had the idea of creating some kind of physical video player with a 4:3 screen that could loop old skate videos. I figured that putting modern videos onto it might be a pain, so I came up with this script to automate the process of converting a video from YouTube. Will I ever actually build the physical player? :shrug:

### The cropping makes the video look dumb

I didn't choose to film it in 16:9... blame someone else.

### Did you just like the dumb pun of the name?

Yes. Like all dumb projects, a good name will give you the impetus to actually finish it.
