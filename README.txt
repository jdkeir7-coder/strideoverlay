Stride Overlay Version 42 — iPhone / DJI MOV audio export fix

WHAT CHANGED
- Extracts AAC audio from camera MOV and MP4 files into an audio-only M4A before decoding.
- Reads movie metadata and small audio chunks, avoiding loading whole 4K clips into memory just to decode audio.
- Maintains original audio timing through video clip splitting, trimming and reordering.
- Stops with a clear message rather than outputting a muted file for unsupported audio codecs.
- On touch-screen phones defaults to 1080p / 30 fps for a more reliable export (60 fps / 4K remain selectable).

TESTING
- Tested the audio extractor against an actual DJI AAC MP4 and a QuickTime MOV remux of that file.
- The extracted M4A passed ffprobe validation and Chromium decoded the AAC successfully.
- A complete MP4 export on iOS Safari must still be tested on an actual device.

DEPLOYMENT
Extract this archive into the published directory of your GitHub Pages repository.
Keep stride-overlay.html, index.html, ads.txt and the brands folder together.
The root index.html redirects to stride-overlay.html.

Stride Overlay Version 41 — Activity upload help and menu logo

Upload both HTML files to your GitHub Pages publishing directory:
- stride-overlay.html : complete editing tool
- index.html : redirects strideoverlay.com to stride-overlay.html

Audio update:
- Original source clip audio is decoded, cut to the same sections as video and encoded into the exported MP4 as AAC.
- When parts are trimmed out, their audio is removed too. Reordered clips retain their own audio.
- If an uploaded clip has no audio, that section is silent.
- When a browser cannot decode or encode detected source audio, export fails visibly instead of silently downloading a muted file.
- The implementation requires a browser with WebCodecs VideoEncoder, AudioEncoder and AAC encoding support.

Known limitations:
- Audio must be decodable by the browser; some unusual audio codecs and some browsers will be unsupported.
- Long or very large files may exceed device memory because browser audio decoding loads sources into memory.
- Browser-level export with actual running footage should be verified before publishing to the live site.

Version 39: Share / AirDrop and Save video buttons now use flat styling and a solid light-green hover/pressed state.

Version 39: iPhone Save to Photos/Share instructions and clearly named Download MP4 button. Verify muxed MP4 audio track presence before offering download.

Version 39: Original Stride Calculator logo now appears next to the Stride Calculator link in the hamburger menu; embedded in the HTML for reliability, and also bundled at brands/stride-calculator.svg.


ADS.TXT SETUP (v40)
The ZIP includes ads.txt at the website publishing root.
After deployment, verify https://strideoverlay.com/ads.txt returns the line below as plain text:
google.com, pub-4255737683434811, DIRECT, f08c47fec0942fa0
This publisher ID was taken from the Stride Overlay HTML. Confirm it matches your AdSense account.
Do not overwrite existing ads.txt entries from any other authorised ad partners; merge them.
An ads.txt file authorises ad sellers but does not guarantee the export advert is served.
Export advert currently uses ad slot 2769991303, configured in the website JavaScript.
Check that the slot and site are approved/active in your AdSense account.


Version 41: Activity upload info button explains where to export GPX / TCX / FIT files and why original FIT or TCX is often preferable for recorded watch splits. The info button is separate from the upload button, so opening help does not open the file picker. The Stride Calculator SVG remains bundled and embedded in the hamburger menu.
