# Bundled FFmpeg 7.0.2

The `ffmpeg` executable in this package was built from the adjacent official
`FFMPEG-SOURCE-7.0.2.tar.xz`. Configuration:

```sh
./configure --disable-doc --disable-debug --disable-ffplay \
  --disable-ffprobe --disable-autodetect --disable-x86asm --prefix=/usr/local
make -j 8 ffmpeg
```

No GPL components or external codec libraries were enabled. FFmpeg reported
`License: LGPL version 2.1 or later`. The corresponding source archive,
configure script and license are included with the installer.
