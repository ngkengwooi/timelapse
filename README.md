# Timelapse

The timelapse script creates a timelapse video from a series of still images. It overlays the timestamp on to each frame/snapshot, so a timer appears in the lower right corner of the video. The timestamp is generated based on the image file names by default, but can be extracted from the metadata (creation date) of the image files.

## Usage

You need to capture the still images separately. This script does not deal with the image capture, but the post-processing. The images should lend themselves to be compiled into a video, e.g., the dimensions should be constant and the camera angle should not change.

1. Place all source images in a single folder.
2. Download the timelapse bash script and save it to an executable path, e.g., /usr/local/bin or ~/.local/bin. This allows you to execute the script anywhere across the file system.
3. `cd` to the folder where you have saved the timelapse script, and make the script executable: `chmod +x timelapse`.
4. In a terminal, `cd` to the source image folder and execute the script: `timelapse`.

By default, the script expects the image file name to reflect the timestamp in the format: \<yyyymmddHHMMSS\>.png. 

The script will:
- Create a ./timestamp folder within the source image folder
- Timestamp the source images and save them to ./timelapse/\<yyyymmddHHMMSS\>.png
- Compile the video and save it as ./timelapse/timelapse.mp4 

These parameters can be changed by passing arguments to the `timelapse` command. Execute `timelapse -h` for details.


## Dependencies

The timelapse script is written for the bash shell, which is shipped with many Linux distributions. You may be able to get it working on other operating systems if you can get the dependencies working, e.g., using the [Windows Subsystem for Linux](https://learn.microsoft.com/en-us/windows/wsl/).

- [bash](https://www.gnu.org/software/bash)
- [exiftool](https://exiftool.org)
- [ffmpeg](https://ffmpeg.org)
- [imagemagick](https://imagemagick.org)
