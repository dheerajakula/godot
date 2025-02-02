# Third party libraries


## assimp

- Upstream: http://github.com/assimp/assimp
- Version: git (d3d98a7ec0c8d38e1952b46dfe53f7e9233dc92d)
- License: BSD-3-Clause


## b2d_convexdecomp

- Upstream: https://github.com/erincatto/Box2D/tree/master/Contributions/Utilities/ConvexDecomposition
- Version: git (25615e0, 2015) with modifications
- License: zlib

The files were adapted to Godot by removing the dependency on b2Math (replacing
it by b2Glue.h) and commenting out some verbose printf calls.
Upstream code has not changed in 10 years, no need to keep track of changes.

Important: Some files have Godot-made changes.
They are marked with `// -- GODOT start --` and `// -- GODOT end --`
comments.


## bullet

- Upstream: https://github.com/bulletphysics/bullet3
- Version: git (5ec8339, 2019)
- License: zlib

Files extracted from upstream source:

- src/* apart from CMakeLists.txt and premake4.lua files
- LICENSE.txt


## certs

- Upstream: Mozilla, via https://apps.fedoraproject.org/packages/ca-certificates
- Version: 2018.2.26
- License: MPL 2.0

File extracted from a recent Fedora install:
/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem
(It can't be extracted directly from the package,
as it's generated on the user's system.)


## cvtt

- Upstream: https://github.com/elasota/cvtt
- Version: 1.0.0-beta4
- License: MIT

Files extracted from upstream source:

- all .cpp, .h, and .txt files in ConvectionKernels/


## enet

- Upstream: http://enet.bespin.org
- Version: 1.3.13
- License: MIT

Files extracted from upstream source:

- all .c files in the main directory (except unix.c win32.c)
- the include/enet/ folder as enet/ (except unix.h win32.h)
- LICENSE file

Important: enet.h, host.c, protocol.c have been slightly modified
to be usable by godot socket implementation and allow IPv6.
Two files (godot.cpp and enet/godot.h) have been added to provide
enet socket implementation using Godot classes.
It is still possible to build against a system wide ENet but doing so
will limit it's functionality to IPv4 only.
Check the diff of enet.h, protocol.c, and host.c with the 1.3.13
tarball before the next update.


## etc2comp

- Upstream: https://github.com/google/etc2comp
- Version: git (9cd0f9c, 2017)
- License: Apache 2.0

Files extracted from upstream source:

- all .cpp and .h files in EtcLib/
- README.md, LICENSE, AUTHORS

Important: Some files have Godot-made changes.
They are marked with `// -- GODOT start --` and `// -- GODOT end --`
comments.


## fonts

### Noto Sans

- Upstream: https://github.com/googlei18n/noto-fonts
- Version: 1.06
- License: OFL-1.1

Use UI font variant if available, because it has tight vertical metrics and good for UI.

### Hack Regular

- Upstream: https://github.com/source-foundry/Hack
- Version: 3.003
- License: MIT + Bitstream Vera License

### DroidSans*.ttf

- Upstream: https://android.googlesource.com/platform/frameworks/base/+/master/data/fonts/
- Version: ? (pre-2014 commit when DroidSansJapanese.ttf was obsoleted)
- License: Apache 2.0


## freetype

- Upstream: https://www.freetype.org
- Version: 2.10.1
- License: FreeType License (BSD-like)

Files extracted from upstream source:

- the `src/` folder, stripped of the `Jamfile` files and the `tools` subfolder
- the `include/` folder
- `docs/{FTL.TXT,LICENSE.TXT}`


## glad

- Upstream: https://github.com/Dav1dde/glad
- Version: 0.1.31
- License: MIT

The files we package are automatically generated.
See the header of glad.c for instructions on how to generate them for
the GLES version Godot targets.


## jpeg-compressor

- Upstream: https://github.com/richgel999/jpeg-compressor
- Version: 1.04
- License: Public domain

Files extracted from upstream source:

- `jpgd.{c,h}`


## libogg

- Upstream: https://www.xiph.org/ogg
- Version: 1.3.3
- License: BSD-3-Clause

Files extracted from upstream source:

- `src/*.c`
- `include/ogg/*.h` in ogg/
- COPYING


## libpng

- Upstream: http://libpng.org/pub/png/libpng.html
- Version: 1.6.37
- License: libpng/zlib

Files extracted from upstream source:

- all .c and .h files of the main directory, except from
  `example.c` and `pngtest.c`
- the arm/ folder
- `scripts/pnglibconf.h.prebuilt` as `pnglibconf.h`
- `LICENSE`


## libsimplewebm

- Upstream: https://github.com/zaps166/libsimplewebm
- Version: git (fe57fd3, 2019)
- License: MIT (main), BSD-3-Clause (libwebm)

This contains libwebm, but the version in use is updated from the one used by libsimplewebm,
and may have *unmarked* alterations from that.

Files extracted from upstream source:

- all the .cpp, .hpp files in the main folder except `example.cpp`
- LICENSE

Important: Some files have Godot-made changes.
They are marked with `// -- GODOT start --` and `// -- GODOT end --`
comments.

## libtheora

- Upstream: https://www.theora.org
- Version: 1.1.1
- License: BSD-3-Clause

Files extracted from upstream source:

- all .c, .h in lib/
- all .h files in include/theora/ as theora/
- COPYING and LICENSE

Upstream patches included in the `patches` directory have been applied
on top of the 1.1.1 source (not included in any stable release yet).


## libvorbis

- Upstream: https://www.xiph.org/vorbis
- Version: 1.3.6
- License: BSD-3-Clause

Files extracted from upstream source:

- `src/*` except from: `lookups.pl`, `Makefile.*`
- `include/vorbis/*.h` as vorbis/
- COPYING


## libvpx

- Upstream: https://chromium.googlesource.com/webm/libvpx/
- Version: 1.6.0
- License: BSD-3-Clause

Files extracted from upstream source:

TODO.

Important: File `libvpx/vpx_dsp/x86/vpx_subpixel_8t_intrin_avx2.c` has
Godot-made change marked with `// -- GODOT --` comments.

The files `libvpx/third_party/android/cpu-features.{c,h}` were copied
from the Android NDK r18.


## libwebp

- Upstream: https://chromium.googlesource.com/webm/libwebp/
- Version: 1.0.2
- License: BSD-3-Clause

Files extracted from upstream source:

- `src/*` except from: .am, .rc and .in files
- AUTHORS, COPYING, PATENTS

Important: The files `utils/bit_reader_utils.{c,h}` have Godot-made
changes to ensure they build for Javascript/HTML5. Those
changes are marked with `// -- GODOT --` comments.


## wslay

- Upstream: https://github.com/tatsuhiro-t/wslay
- Version: 1.1.0
- License: MIT

File extracted from upstream release tarball:

- All `*.c` and `*.h` in `lib/` and `lib/includes/`
- `wslay.h` has a small Godot addition to fix MSVC build.
  See `thirdparty/wslay/msvcfix.diff`

## mbedtls

- Upstream: https://tls.mbed.org/
- Version: 2.16.2
- License: Apache 2.0

File extracted from upstream release tarball (`-apache.tgz` variant):
- All `*.h` from `include/mbedtls/` to `thirdparty/mbedtls/include/mbedtls/`
- All `*.c` from `library/` to `thirdparty/mbedtls/library/`
- Applied the patch in `thirdparty/mbedtls/1453.diff` (PR 1453).
  Soon to be merged upstream. Check it out at next update.
- Applied the patch in `thirdparty/mbedtls/padlock.diff`. This disables VIA
  padlock support which defines a symbol `unsupported` which clashes with
  a symbol in libwebsockets.
- Added 2 files `godot_core_mbedtls_platform.{c,h}` providing configuration
  for light bundling with core.


## miniupnpc

- Upstream: https://github.com/miniupnp/miniupnp/tree/master/miniupnpc
- Version: git (3cf6efa, 2019)
- License: BSD-3-Clause

Extract only the `miniupnpc` folder inside `thirdparty/miniupnpc`.
Exclude all non `.c` and `.h` files, plus all files beginning with `test`
`minihttptestserver.c` and `wingenminiupnpcstrings.c`.

The only modified file is miniupnpcstrings.h, which was created for Godot
(it is usually autogenerated by cmake).


## minizip

- Upstream: http://www.zlib.net
- Version: 1.2.11 (zlib contrib)
- License: zlib

Files extracted from the upstream source:

- contrib/minizip/{crypt.h,ioapi.{c,h},zip.{c,h},unzip.{c,h}}

Important: Some files have Godot-made changes for use in core/io.
They are marked with `/* GODOT start */` and `/* GODOT end */`
comments and a patch is provided in the minizip/ folder.


## misc

Collection of single-file libraries used in Godot components.

### core

- `clipper.{cpp,hpp}`
  * Upstream: https://sourceforge.net/projects/polyclipping
  * Version: 6.4.2 + Godot changes (added optional exceptions handling)
  * License: BSL-1.0
- `fastlz.{c,h}`
  * Upstream: https://github.com/ariya/FastLZ
  * Version: git (f121734, 2007)
  * License: MIT
- `hq2x.{cpp,h}`
  * Upstream: https://github.com/brunexgeek/hqx
  * Version: TBD, file structure differs
  * License: Apache 2.0
- `open-simplex-noise.{c,h}`
  * Upstream: https://github.com/smcameron/open-simplex-noise-in-c
  * Version: git (0d555e7, 2015)
  * License: Unlicense
- `pcg.{cpp,h}`
  * Upstream: http://www.pcg-random.org
  * Version: minimal C implementation, http://www.pcg-random.org/download.html
  * License: Apache 2.0
- `smaz.{c,h}`
  * Upstream: https://github.com/antirez/smaz
  * Version: git (150e125, 2009)
  * License: BSD-3-Clause
  * Modifications: use `const char*` instead of `char*` for input string
- `triangulator.{cpp,h}`
  * Upstream: https://github.com/ivanfratric/polypartition (`src/polypartition.cpp`)
  * Version: TBD, class was renamed
  * License: MIT

### modules

- `curl_hostcheck.{c,h}`
  * Upstream: https://curl.haxx.se/
  * Version: ? (2013)
  * License: MIT
- `yuv2rgb.h`
  * Upstream: http://wss.co.uk/pinknoise/yuv2rgb/ (to check)
  * Version: ?
  * License: BSD

### platform

- `ifaddrs-android.{cc,h}`
  * Upstream: https://chromium.googlesource.com/external/webrtc/stable/talk/+/master/base/ifaddrs-android.h
  * Version: git (5976650, 2013)
  * License: BSD-3-Clause

### scene

- `easing_equations.cpp`
  * Upstream: http://robertpenner.com/easing/ via https://github.com/jesusgollonet/ofpennereasing (modified to fit Godot types)
  * Version: git (af72c14, 2008) + Godot types and style changes
  * License: BSD-3-Clause
- `mikktspace.{c,h}`
  * Upstream: https://wiki.blender.org/index.php/Dev:Shading/Tangent_Space_Normal_Maps
  * Version: 1.0
  * License: zlib
- `stb_truetype.h`
  * Upstream: https://github.com/nothings/stb
  * Version: 1.21
  * License: Public Domain (Unlicense) or MIT
- `stb_vorbis.c`
  * Upstream: https://github.com/nothings/stb
  * Version: 1.16
  * License: Public Domain (Unlicense) or MIT


## nanosvg

- Upstream: https://github.com/memononen/nanosvg
- Version: git (c1f6e20, 2018)
- License: zlib

Files extracted from the upstream source:

- All .h files in `src/`
- LICENSE.txt


## opus

- Upstream: https://opus-codec.org
- Version: 1.1.5 (opus) and 0.8 (opusfile)
- License: BSD-3-Clause

Files extracted from upstream source:

- all .c and .h files in src/ (both opus and opusfile)
- all .h files in include/ (both opus and opusfile) as opus/
- remove unused `opus_demo.c`,
- remove `http.c`, `wincerts.c` and `winerrno.h` (part of
  unused libopusurl)
- celt/ and silk/ subfolders
- COPYING


## pcre2

- Upstream: http://www.pcre.org
- Version: 10.33
- License: BSD-3-Clause

Files extracted from upstream source:

- Files listed in the file NON-AUTOTOOLS-BUILD steps 1-4
- All .h files in src/ apart from pcre2posix.h
- src/pcre2_jit_compile.c
- src/pcre2_jit_match.c
- src/pcre2_jit_misc.c
- src/sljit/*
- AUTHORS and LICENCE


## pvrtccompressor

- Upstream: https://bitbucket.org/jthlim/pvrtccompressor
- Version: hg (cf71777, 2015)
- License: BSD-3-Clause

Files extracted from upstream source:

- all .cpp and .h files apart from `main.cpp`
- LICENSE.TXT


## recastnavigation

- Upstream: https://github.com/recastnavigation/recastnavigation
- version: git (ef3ea40f, 2017)
- License: zlib

Files extracted from upstream source:

- `Recast/` folder
- License.txt


## squish

- Upstream: https://sourceforge.net/projects/libsquish
- Version: 1.15
- License: MIT

Files extracted from upstream source:

- all .cpp, .h and .inl files

Important: Some files have Godot-made changes.
They are marked with `// -- GODOT start --` and `// -- GODOT end --`
comments and a patch is provided in the squish/ folder.


## tinyexr

- Upstream: https://github.com/syoyo/tinyexr
- Version: git (65f9859, 2018)
- License: BSD-3-Clause

Files extracted from upstream source:

- `tinyexr.{cc,h}`


## vhacd

- Upstream: https://github.com/kmammou/v-hacd
- Version: git (2297aa1, 2018)
- License: BSD-3-Clause

Files extracted from upstream source:

- From `src/VHACD_Lib/`: `inc`, `public` and `src`
- `LICENSE`

Some downstream changes have been made and are identified by
`// -- GODOT start --` and `// -- GODOT end --` comments.
They can be reapplied using the patches included in the `vhacd`
folder.


## xatlas

- Upstream: https://github.com/jpcy/xatlas
- Version: git (b7d7bb, 2019)
- License: MIT

Files extracted from upstream source:

- `xatlas.{cpp,h}`

Note: License is marked as Public Domain in the files, but it was
later clarified upstream to MIT license.


## zlib

- Upstream: http://www.zlib.net
- Version: 1.2.11
- License: zlib

Files extracted from upstream source:

- all .c and .h files


## zstd

- Upstream: https://github.com/facebook/zstd
- Version: 1.4.0
- License: BSD-3-Clause

Files extracted from upstream source:

- lib/{common/,compress/,decompress/,zstd.h}
- LICENSE
