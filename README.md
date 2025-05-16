# BigEye
Pull or Push RTMP, RTSP, SRT with Recording MP4 and Viewing via HLS

## Install
Extract the .zip file to a directory.

When ./bigeye is ran it there will be several files placed in a "BigEye" directory residing in 
the same directory as the executable.

## Initial Configuration
An admin user is required to login.

This user can be added via:

```bash
bigeye --add-admin-email='user@host.tld'
```

## Sources
Push and Pull sources are allowed.

A push source will connect to the server via a specified path.

A pull source will be connected to.

For example, if a RTSP camera pull source is configured, the server will connect to the camera via RTSP.

Both types can be recorded to mp4 or viewed via HLS.

The "Path" option is the viewable HLS path for the source.

## Profiles
A profile is used to associate a set of viewers with a Grid.

## Grids
A grid is a set of sources that can be viewed via HLS.
