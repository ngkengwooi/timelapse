# Timelapse

The timelapse script creates a timelapse video from a series of still images. It overlays the timestamp on to each frame/snapshot, so a ticking clock appears in the lower right corner of the video. The timestamp is extracted from the metadata (creation date) of the image files.

## Usage

You need to capture the still images separately. This script does not deal with the image capture, but the post-processing. The images should lend themselves to be compiled into a video, e.g., the dimensions should be constant and the camera angle should not change.

1. Place all source images in a single folder.
2. Download the timelapse bash script and save it to an executable path, e.g., /usr/local/bin or ~/.local/bin. This allows you to execute the script anywhere across the file system. Alternatively, you may save the script to the same folder containing the source images and execute it only within that folder.
3. `cd` to the folder where you have saved the timelapse script, and make the script executable: `chmod +x timelapse`.
4. In a terminal, `cd` to the source image folder.
5. Execute the script:

   - `timelapse` if you've installed it to an executable path
   - `./timestamp` if you're executing it from the source image folder
     
6. The snapshots and the video can be found under ./outdir.

## Dependencies

The timelapse script is written for the bash shell, which is shipped with many Linux distributions. You may be able to get it working on other operating systems if you can get the dependencies working, e.g., using the [Windows Subsystem for Linux](https://www.howtogeek.com/249966/how-to-install-and-use-the-linux-bash-shell-on-windows-10/).

- bash
- exiftool
- ffmpeg
- imagemagick
