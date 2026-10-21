STRIDE OVERLAY — VERSION 44 (AUDIO PRESERVATION)

INSTALLATION
Extract all files into the publishing directory of your GitHub Pages repo.
index.html is the actual homepage at https://strideoverlay.com/; stride-overlay.html is a matching named copy.

MOBILE AUDIO EXPORT
Original AAC audio packets from supported MOV/MP4 source clips now pass directly into the exported MP4, retaining the camera's original encoded sound without re-encoding on mobile Safari. This supports trims, splits and rearranged clips. Silent clips are padded with audio silence to keep timing aligned.
For non-AAC or unsupported source formats the existing browser audio-processing fallback is used, and errors must not be silently ignored.

TEST
1. Upload an iPhone or DJI recording with sound and the corresponding GPX.
2. Export a 5-second video at 1080p and 30 fps.
3. Listen in the iPhone Files app and in Photos after saving from Share.
4. Test a two-clip montage and check sound after each cut.

Do not treat a browser test as proof of native iPhone compatibility. If the sound is missing, retain the original video and report the model, iOS version and original recording format.
