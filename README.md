<br />
<p align="center">
  <a href="https://github.com/owncast/owncast" alt="Owncast">
    <img src="https://owncast.online/images/logo.png" alt="Logo" width="200">
  </a>
</p>

<br/>

  <p align="center">
    <strong>Take control over your content and stream it yourself.</strong>
    <br />
    <a href="https://owncast.online"><strong>Explore the docs »</strong></a>
    <br />
    <a href="https://watch.owncast.online/">View Demo</a>
    ·
    <a href="https://broadcast.owncast.online/">Use Our Server for Testing</a>
    ·
    <a href="https://owncast.online/faq/">FAQ</a>
    ·
    <a href="https://github.com/owncast/owncast/issues">Report Bug</a>
  </p>
</p>

---

# <p align="center"> Owncast windows fix/mod </p>

## Getting Started

I created this small fix by modifying only two files to make FFmpeg work on Windows. It was written quickly, with some help from ChatGPT, so it's not perfect. I'm publishing this as an unfinished but functional fix. I removed the RTMP Output settings and added my own modifications in transcoder.go. For now, it works at 0.1.3 version.

### Backend

The Owncast backend is a service written in Go.

1. Ensure you have prerequisites installed.
   - C compiler, like MinGW
   - [ffmpeg](https://ffmpeg.org/download.html),  tested on ffmpeg-2024-06-27-git-9a3bc59a38-full_build
1. Install the [Go toolchain](https://golang.org/dl/) (1.21 or above).
1. Download source. `https://github.com/owncast/owncast/archive/refs/tags/v0.1.3.zip` 
1. put `ffmpeg.exe` in projcet folder or add it to PATH
1. paste `utils/utils.go` and `core/transcoder/transcoder.go` from repo
1. `go run main.go` will run from the source. or go run build and run exe
1. Visit `http://yourserver:8080` to access the web interface or `http://yourserver:8080/admin` to access the admin.
1. Point your [broadcasting software](https://owncast.online/docs/broadcasting/) at your new server and start streaming.

### Frontend

The frontend is the web interface that includes the player, chat, embed components, and other UI.

1. This project lives in the `web` directory.
1. Run `npm install` to install the Javascript dependencies, maybe some `npm audit`.
1. Run `npm run dev`

## TODO

### transcoder.go
1. t.getVariantsString(),
```
time="2024-12-18T20:38:04+01:00" level=error msg="[AVFormatContext @ 000001cd19b7d040] Unable to choose an output format for '\"'; use a standard extension for the filename or specify the format manually."
time="2024-12-18T20:38:04+01:00" level=error msg="[out#0 @ 000001cd1963ecc0] Error initializing the muxer for \": Invalid argument"
time="2024-12-18T20:38:04+01:00" level=error msg="Error opening output file \"."
time="2024-12-18T20:38:04+01:00" level=error msg="Error opening output files: Invalid argument"
time="2024-12-18T20:38:04+01:00" level=error msg="transcoding error. look at data/logs/transcoder.log to help debug. your copy of ffmpeg may not support your selected codec of libx264 https://owncast.online/docs/codecs/"
exit status 0xc000013a
```
### web
npm run dev make it run normal
```
Error: Could not find a production build in the '.next' directory. Try building your app with 'next build' before starting the production server. https://nextjs.org/docs/messages/production-start-no-build-id
    at setupFsCheck (C:\Users\jakub\Downloads\owncast-0.1.3\web\node_modules\next\dist\server\lib\router-utils\filesystem.js:151:19)
    at async initialize (C:\Users\jakub\Downloads\owncast-0.1.3\web\node_modules\next\dist\server\lib\router-server.js:62:23)
    at async Server.<anonymous> (C:\Users\jakub\Downloads\owncast-0.1.3\web\node_modules\next\dist\server\lib\start-server.js:249:36)
```

<!-- LICENSE -->

## License

Distributed under the MIT License. 
