# chromakey

live green screen solution with ffmpeg and v4l2 pseudo device

In order to get this work you need to have a recent kernel with v4l2 loopback device enabled, and ffmpeg 3.4 or greater with chroma key support

```bash
sudo apt install v4l2loopback-utils v4l2loopback-dkms ffmpeg
sudo modprobe v4l2loopback # creates pseudo device probably /dev/video1
```

Download and copy this script into `/usr/local/bin` then execute with

```
chromakey -i path_to_background_image.png -k 0xcolor_in_hexadecimal 
```

The live chromakey-ed videostream will be available on specified output device, usually `/dev/video1` and can be checked with ay v4l2 compatible device
here is firefox:
`https://webrtc.github.io/samples/src/content/devices/input-output/`
Skype also known to work.

