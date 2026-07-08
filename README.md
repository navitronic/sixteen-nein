# sixteen-nein

Shell scripts for downloading a YouTube video, centre-cropping it to 4:3, and running it through `ntsc-rs-cli`.

## Requirements

Install these commands before running the script:

- `yt-dlp`
- `ffmpeg`
- `ntsc-rs-cli`

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
