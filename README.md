# BigEye
Headless web server with live streaming support.

RTMP, RTSP, and SRT live streams are supported, either push or pull.

The streams can be recorded to MP4 and viewed via LLHLS.

## Install
Extract the .zip file to a directory.

When ./bigeye is ran it there will be several files placed in a "BigEye" directory residing in 
the same directory as the executable.

## Admin Setup
An admin user is required to login.

This user can be added via:

```bash
./bigeye --add-admin-email='user@host.tld'
```

## Free Limits
By default the free version is limited to 30 connections and two auto started sources.

## Running

Running `bigeye` with no arguments launches the web server. The log direcotry is output to the console. This is very important for getting feedback on the running system. Further, the listening ip and port are shown. By default, all IPv4 interfaces are listenend on port 8080.

Hit CTRL-C at any time to exit (you may need to press CTRL-C multiple times).

```bash
./bigeye
[20:16:33 INF] BigEye: RTMP, RTSP, SRT Recording MP4, Viewing via LLHLS
...
[20:16:33 INF] Email support: brian@sparksandmagic.com
...
[20:16:33 INF] LogDirectory: /home/bpm/BigEyeBaseDirectory/BigEye/Log
...
[20:16:35 INF] Now Listening on: http://0.0.0.0:8080
...
[20:16:35 INF] Application started. Press Ctrl+C to shut down.

```

## Configuration
The heart of the app is recording and viewing live streams.

Each live stream is called a source.

To view a source a profile and grid are needed.

The profile determines who has access to the sources and the grid defines which sources are shown to the user.

It's a "grid" of sources presented via a web page.

For example, a 2x2 set of cells, or four sources could be presented via HLS.js and LLHLS.

The hierarchy, from top to bottom is Grid (and Grid Cells) -> Profile -> Sources.

In addition, a source can be recorded.

Step 1 is setting up some sources.

Step 2 is setting up a profile.

Step 3 is setting up a grid.

Then view or record.

## Sources
Push and Pull sources are allowed.

A push source will connect to the server via a specified path.

A pull source will be connected to.

For example, if a RTSP camera pull source is configured, the server will connect to the camera via RTSP.

Both types can be recorded to mp4 or viewed via HLS.

The "Path" option is the viewable HLS path for the source. It will be presented to the user via http://ip:port/hls/path

## Profiles
A profile is used to associate a set of viewers with a Grid. You don't need to define any viewers, but you need a profile for a grid.

By default, an admin can view any profile.

## Grids
A grid is a set of sources that can be viewed via HLS.

By default an admin can view any grid.

## Recordings
If enabled, recordings are kept on disk until expired.

The app will delete them via the absolute path they were created with.
