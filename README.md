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

I created this small fix by modifying only two files to make FFmpeg work on Windows. It was written quickly, with some help from ChatGPT, so it's not perfect. I'm publishing this as an unfinished but functional fix. For now, it works at 0.1.3 version.

# How to

## compiled server check <a href="https://github.com/jakubix30/Owncast-windows-fix/releases">latest release</a>
OR
## Build your own 

### Backend

The Owncast backend is a service written in Go.

1. Ensure you have prerequisites installed.
   - C compiler, like MinGW
   - [ffmpeg](https://ffmpeg.org/download.html),  tested on ffmpeg-2024-06-27-git-9a3bc59a38-full_build
1. Install the [Go toolchain](https://golang.org/dl/) (1.21 or above).
1. Download source. `https://github.com/owncast/owncast/archive/refs/tags/v0.1.3.zip` 
1. put `ffmpeg.exe` in projcet folder or add it to PATH
1. paste files to owncast folder from repo
1. `go run main.go` will run from the source. or `go build` and run exe
1. Visit `http://yourserver:8080` to access the web interface or `http://yourserver:8080/admin` to access the admin.
1. Point your [broadcasting software](https://owncast.online/docs/broadcasting/) at your new server and start streaming.
1. That it's, now run server by `go run main.go` or builded exe

### Frontend (not needed)

The frontend is the web interface that includes the player, chat, embed components, and other UI.

1. This project lives in the `web` directory.
1. Run `npm install` to install the Javascript dependencies, maybe some `npm audit`.
1. Run `npm run dev`

## TODO


<!-- LICENSE -->

## License

This project is based on Owncast (https://github.com/owncast/owncast), distributed under the MIT License.
