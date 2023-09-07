# Timelapse

The `timelapse` script creates a timelapse video from a series of still images. It overlays the timestamp on to each frame/snapshot, so that a ticking timer appears in the video. The timestamp is generated based on the image file name by default. The script also includes an option to first rename the image file to reflect the timestamp in the metadata (creation date), although not all image capture devices record this metadata and so the images they create may not support this option.

## Usage

You need to capture the still images separately. This script does not deal with the image capture, but the post-processing. The images should lend themselves to be compiled into a video, e.g., the dimensions should be constant and the camera angle should not change.

On a Linux computer:

1. Place all source images in a single folder. The folder should only contain the source images and nothing else.
2. Download the `timelapse` script and save it to an executable path, e.g., `/usr/local/bin` or `~/.local/bin`. This allows you to execute the script anywhere across the file system.
3. `cd` to the folder where you have saved the `timelapse` script, and make the script executable: `chmod +x timelapse`.
4. In a terminal, `cd` to the source image folder and execute the script: `timelapse`. This command supports the PNG image format by default. If your images are in a different format, you will need to configure `timelapse` to use them.

By default, the script will:

- Create a `./timestamp` folder within the source image folder
- Timestamp the source images and save them to `./timelapse/<yyyymmddHHMMSS>.png`
- Compile the video and save it as `./timelapse/timelapse.mp4`.

## Configuration

The behaviour of `timelapse` can be configured by passing certain arguments to the `timelapse` command. For details, execute `timelapse -h`.

By default, the script expects the image file name to reflect the timestamp in the format: `<yyyymmddHHMMSS>.png`. Variants including delimiters (e.g., `yyyy-mm-dd-HH-MM-SS.png`) are acceptable. The script will strip the file name of any non-numerical characters to generate the timestamp. The file name must correspond to a valid timestamp in the format `yyyymmddHHMMSS` when stripped of such characters. The file extension can vary depending on the file format. The script supports most common image file formats (e.g., with extensions .jpg, .tif, .bmp, .webp) as long as imagemagick can convert them into the PNG format. However, all the images in the series must be of the same format.

The position of the timestamp and its appearance can also be configured. 

## Renaming files using third-party tools

The following tools can be used to rename the image files to the required format (e.g., `<yyyymmddHHMMSS>.png`) in bulk before running `timelapse`:

- [Thunar Bulk Renamer](https://docs.xfce.org/xfce/thunar/bulk-renamer/start)
- [GPRename](https://gprename.sourceforge.net)
- [ReNamer](https://www.den4b.com/products/renamer)

## Dependencies

The timelapse script is written for the bash shell, which is shipped with many Linux distributions. You may be able to get it working on other operating systems if you can get the dependencies working, e.g., using the [Windows Subsystem for Linux](https://learn.microsoft.com/en-us/windows/wsl/).

- [bash](https://www.gnu.org/software/bash)
- [exiftool](https://exiftool.org)
- [ffmpeg](https://ffmpeg.org)
- [imagemagick](https://imagemagick.org)
