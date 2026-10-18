Stride Overlay Version 38 — Original audio preservation

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

Version 38: Share / AirDrop and Save video buttons now use flat styling and a solid light-green hover/pressed state.

Version 38: iPhone Save to Photos/Share instructions and clearly named Download MP4 button. Verify muxed MP4 audio track presence before offering download.
