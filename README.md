# Timelapse

Timelapse macro photography for laboratory investigations

The bash script timelapse creates a timelapse video from a series of still images. It overlays the timestamp on to each frame/snapshot, so a ticking clock appears in the video. The timestamp is extracted from the metadata (creation date) of the image file.

## Usage

1. Download the timelapse bash script and save it to a suitable location, e.g., /usr/loca/bin or ~/.local/bin.
2. Make sure the timelapse bash script is executable: `chmd +x timelapse`
3. Place the source images in a single folder.
4. In a terminal, `cd` to the source image folder.
5. Execute the script: `./timelapse`.
6. The snapshots and the video can be found under ./outdir.

## Dependencies
- exiftool
- ffmpeg
- imagemagick
