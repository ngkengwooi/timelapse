# Timelapse

Timelapse macro photography for laboratory investigations.

The bash script timelapse creates a timelapse video from a series of still images. It overlays the timestamp on to each frame/snapshot, so a ticking clock appears in the lower right corner of the video. The timestamp is extracted from the metadata (creation date) of the image files.

## Usage

1. Download the timelapse bash script and save it to a suitable location, e.g., /usr/loca/bin or ~/.local/bin.
2. Make sure the timelapse bash script is executable: `chmd +x timelapse`
3. Place the source images in a single folder.
4. In a terminal, `cd` to the source image folder.
5. Execute the script: `./timelapse`.
6. The snapshots and the video can be found under ./outdir.

## Dependencies

The timelapse script is written for the bash shell, which is shipped with many Linux distributions. You may be able to get it working on other operating systems if you can get the dependencies working, e.g., using the [Windows Subsystem for Linux](https://www.howtogeek.com/249966/how-to-install-and-use-the-linux-bash-shell-on-windows-10/).

- bash
- exiftool
- ffmpeg
- imagemagick
