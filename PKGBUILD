# Maintainer: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# Contributor: Jan de Groot <jgc@archlinux.org>

pkgbase=gstreamer-qti-oss
pkgname=(
  gstreamer-qti-oss
  gst-plugins-bad-libs-qti-oss   # Split badaudio first
  gst-plugins-base-libs-qti-oss
  gst-plugins-base-qti-oss
  gst-plugins-good-qti-oss
  gst-plugins-bad-qti-oss
  gst-plugins-ugly-qti-oss
  gst-libav-qti-oss
  gst-plugin-gtk-qti-oss
  gst-plugin-hip-qti-oss
  gst-plugin-msdk-qti-oss
  gst-plugin-onnx-qti-oss
  gst-plugin-opencv-qti-oss
  gst-plugin-qml6-qti-oss
  gst-plugin-qmlgl-qti-oss
  gst-plugin-qsv-qti-oss
  gst-plugin-va-qti-oss
  gst-plugin-wpe-qti-oss
  gst-plugin-wpe2-qti-oss
  gst-devtools-libs-qti-oss
  gst-devtools-qti-oss
  gst-rtsp-server-qti-oss
  gst-editing-services-qti-oss
  gst-python-qti-oss
)
pkgver=1.28.0
pkgrel=4
pkgdesc="Multimedia graph framework"
url="https://gstreamer.freedesktop.org/"
arch=('aarch64')
license=(LGPL-2.1-or-later)
makedepends=(
  a52dec
  aalib
  alsa-lib
  aom
  bash-completion
  bluez-libs
  bzip2
  cairo
  cdparanoia
  chromaprint
  curl
  faac
  faad2
  ffmpeg
  flac
  fluidsynth
  gdk-pixbuf2
  git
  glib2
  glib2-devel
  glibc
  gobject-introspection
  graphene
  gsm
  gtk3
  hicolor-icon-theme
  imath
  iso-codes
  jack2
  json-glib
  ladspa
  lame
  lcms2
  libass
  libavc1394
  libavtp
  libbs2b
  libcaca
  libcap
  libcdio
  libdc1394
  libdca
  libde265
  libdrm
  libdv
  libdvdnav
  libdvdread
  libelf
  libfdk-aac
  libfreeaptx
  libgcc
  libglvnd
  libgme
  libgudev
  libiec61883
  libjpeg-turbo
  liblc3
  libldac
  liblrdf
  libltc
  libmicrodns
  libmodplug
  libmpcdec
  libmpeg2
  libnice
  libogg
  libopenmpt
  libpng
  libpulse
  libraw1394
  librsvg
  libshout
  libsndfile
  libsoup3
  libsrtp
  libstdc++
  libtheora
  libunwind
  libusb
  libva
  libvorbis
  libvpl
  libvpx
  libwebp
  libwpe
  libx11
  libxcb
  libxdamage
  libxext
  libxfixes
  libxi
  libxkbcommon
  libxkbcommon-x11
  libxml2
  libxrandr
  libxtst
  libxv
  lilv
  lv2
  mesa
  meson
  mjpegtools
  mpg123
  nasm
  neon
  nettle
  onnxruntime
  openal
  opencore-amr
  opencv
  openexr
  openh264
  openjpeg2
  openssl
  opentimelineio
  opus
  orc
  pango
  python
  python-cairo
  python-commonmark
  python-gobject
  python-lxml
  python-setuptools
  python-typing_extensions
  qrencode
  qt5-base
  qt5-declarative
  qt5-tools
  qt5-wayland
  qt5-x11extras
  qt6-base
  qt6-declarative
  qt6-shadertools
  qt6-tools
  rtmpdump
  rust
  sbc
  sdl2
  shaderc
  soundtouch
  spandsp
  speex
  srt
  svt-av1
  svt-hevc
  systemd-libs
  taglib
  twolame
  v4l-utils
  valgrind
  vmaf
  vulkan-headers
  vulkan-icd-loader
  vulkan-validation-layers
  wavpack
  wayland
  wayland-protocols
  webrtc-audio-processing-1
  wildmidi
  wpebackend-fdo
  wpewebkit
  x264
  x265
  zbar
  zlib
  zvbi
  zxing-cpp
)
# checkdepends=(xorg-server-xvfb)
source=(
  "git+https://gitea.classfun.cn:4443/mirrors/gstreamer.git#tag=$pkgver"
  0001-HACK-meson-Disable-broken-tests.patch
  0002-Fix-build-with-zxing-cpp-3.patch
  # gst-qti-oss-patches (base/good/bad prefix = subproject)
  base_0001-video-Add-support-for-NV12_Q08C-compressed-8-bit-for.patch
  base_0002-video-Add-support-for-NV12_Q10LE32C-compressed-10-bi.patch
  base_0003-videometa-Update-the-aggregation-logic-for-stride-al.patch
  good_0001-v4l2-Add-support-for-V4L2_PIX_FMT_QC08C-format.patch
  good_0002-v4l2videoenc-Set-format-on-capture-queue-before-enco.patch
  good_0003-v4l2-Add-v4l2av1dec-stateful-decoder-support.patch
  good_0004-v4l2videodec-Prefer-colorimetry-from-acquired-caps.patch
  good_0005-v4l2object-providing-aligned-size-when-propose-alloc.patch
  good_0006-v4l2-Drop-empty-bytesused-0-buffers.patch
  good_0007-v4l2-Handle-GAP-buffer-in-encoder.patch
  good_0008-v4l2-Add-support-for-V4L2_PIX_FMT_QC10C-format.patch
  bad_0001-wayland-Add-support-for-NV12_Q08C-compressed-8-bit.patch
  bad_0002-waylandsink-Release-pending-buffers-during-PAUSED-to.patch
  bad_0003-waylandsink-support-gap-buffers.patch
)
b2sums=('SKIP'
        'SKIP'
        'SKIP'
        'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP')

prepare() {
  cd gstreamer

  # Disable broken tests
  git apply -3 ../0001-HACK-meson-Disable-broken-tests.patch

  # Fix build with zxing-cpp 3
  git apply -3 ../0002-Fix-build-with-zxing-cpp-3.patch

  # gst-qti-oss-patches (Qualcomm OSS) - base_/good_/bad_ → subprojects
  for p in ../base_*.patch; do
    git apply -3 --directory=subprojects/gst-plugins-base "$p"
  done
  for p in ../good_*.patch; do
    git apply -3 --directory=subprojects/gst-plugins-good "$p"
  done
  for p in ../bad_*.patch; do
    git apply -3 --directory=subprojects/gst-plugins-bad "$p"
  done
}

build() {
  local meson_options=(
    -D benchmarks=disabled
    -D examples=disabled
    -D glib_debug=disabled
    -D gpl=enabled
    -D gst-devtools:debug_viewer=enabled
    -D gst-examples=disabled
    -D gst-plugins-bad:aja=disabled
    -D gst-plugins-bad:amfcodec=disabled
    -D gst-plugins-bad:androidmedia=disabled
    -D gst-plugins-bad:cuda-nvmm=disabled
    -D gst-plugins-bad:directfb=disabled
    -D gst-plugins-bad:directshow=disabled
    -D gst-plugins-bad:flite=disabled
    -D gst-plugins-bad:gs=disabled
    -D gst-plugins-bad:iqa=disabled
    -D gst-plugins-bad:isac=disabled
    -D gst-plugins-bad:lcevcdecoder=disabled
    -D gst-plugins-bad:lcevcencoder=disabled
    -D gst-plugins-bad:magicleap=disabled
    -D gst-plugins-bad:mfx_api=oneVPL
    -D gst-plugins-bad:nvcomp=disabled
    -D gst-plugins-bad:nvdswrapper=disabled
    -D gst-plugins-bad:openni2=disabled
    -D gst-plugins-bad:opensles=disabled
    -D gst-plugins-bad:qt6d3d11=disabled
    -D gst-plugins-bad:svthevcenc=disabled
    -D gst-plugins-bad:svtjpegxs=disabled
    -D gst-plugins-bad:tinyalsa=disabled
    -D gst-plugins-bad:voaacenc=disabled
    -D gst-plugins-bad:voamrwbenc=disabled
    -D gst-plugins-bad:wasapi2=disabled
    -D gst-plugins-bad:wasapi=disabled
    -D gst-plugins-bad:mpeghdec=disabled
    -D gst-plugins-bad:tflite=disabled
    -D gst-plugins-base:libvisual=disabled
    -D gst-plugins-base:tremor=disabled
    -D gst-plugins-good:rpicamsrc=disabled
    -D gst-plugins-ugly:sidplay=disabled
    -D gstreamer:dbghelp=disabled
    -D gstreamer:ptp-helper-permissions=capabilities
    -D libnice=disabled
    -D orc-source=system
    -D package-name="Arch Linux GStreamer ${epoch:+$epoch:}$pkgver-$pkgrel"
    -D package-origin="https://www.archlinux.org/"
  )

  # https://gitlab.freedesktop.org/gstreamer/gstreamer/-/issues/3197
  export GI_SCANNER_DISABLE_CACHE=1

  # Cargo sub-build: Use debug and LTO
  export CARGO_PROFILE_RELEASE_DEBUG=2 CARGO_PROFILE_RELEASE_STRIP=false
  export CARGO_PROFILE_RELEASE_LTO=true CARGO_PROFILE_RELEASE_CODEGEN_UNITS=1

  arch-meson gstreamer build "${meson_options[@]}"
  meson compile -C build
}

# check() (
#   export XDG_RUNTIME_DIR="$PWD/runtime-dir"
#   mkdir -p -m 700 "$XDG_RUNTIME_DIR"

#   export CK_TIMEOUT_MULTIPLIER=5
#   export NO_AT_BRIDGE=1 GTK_A11Y=none

#   # Flaky due to timeouts
#   xvfb-run -s "-nolisten local" \
#     meson test -C build --print-errorlogs -t $CK_TIMEOUT_MULTIPLIER
# )

_install() {
  local src dir
  for src in "${files[@]}"; do
    dir="$pkgdir/$(dirname "$src")"
    mkdir -p "$dir"
    mv -v "$src" "$dir"
  done
}

package_gstreamer-qti-oss() {
  pkgdesc+=" - core (with Qualcomm patches)"
  depends=(
    glib2
    glibc
    libcap
    libelf
    libgcc
    libunwind
    gst-plugins-bad-libs-qti-oss
    gst-plugins-base-libs-qti-oss
    gst-plugins-base-qti-oss
    gst-plugins-good-qti-oss
    gst-plugins-bad-qti-oss
    gst-plugins-ugly-qti-oss
    gst-libav-qti-oss
    gst-plugin-gtk-qti-oss
    gst-plugin-hip-qti-oss
    gst-plugin-msdk-qti-oss
    gst-plugin-onnx-qti-oss
    gst-plugin-opencv-qti-oss
    gst-plugin-qml6-qti-oss
    gst-plugin-qmlgl-qti-oss
    gst-plugin-qsv-qti-oss
    gst-plugin-va-qti-oss
    gst-plugin-wpe-qti-oss
    gst-plugin-wpe2-qti-oss
    gst-devtools-libs-qti-oss
    gst-devtools-qti-oss
    gst-rtsp-server-qti-oss
    gst-editing-services-qti-oss
    gst-python-qti-oss
  )
  optdepends=("python: gst-plugins-doc-cache-generator")
  provides=("gstreamer=$pkgver-$pkgrel")
  conflicts=('gstreamer' 'gstreamer-vaapi<=1.26.10-5')
  install=gstreamer.install

  meson install -C build --destdir "$srcdir/root"

  cd root; local files=(
    usr/include/gstreamer-1.0/gst/{base,check,controller,net,*.h}
    usr/lib/libgst{reamer,base,check,controller,net}-1.0.so*
    usr/lib/pkgconfig/gstreamer{,-base,-check,-controller,-net}-1.0.pc
    usr/lib/girepository-1.0/Gst{,Base,Check,Controller,Net}-1.0.typelib
    usr/share/gir-1.0/Gst{,Base,Check,Controller,Net}-1.0.gir

    usr/lib/gstreamer-1.0/gst-{completion,ptp}-helper
    usr/lib/gstreamer-1.0/gst-{hotdoc-plugins,plugin}-scanner
    usr/lib/gstreamer-1.0/gst-plugins-doc-cache-generator
    usr/lib/gstreamer-1.0/libgstcoreelements.so
    usr/lib/gstreamer-1.0/libgstcoretracers.so

    usr/share/locale/*/LC_MESSAGES/gstreamer-1.0.mo

    usr/bin/gst-{inspect,launch,stats,tester,typefind}-1.0
    usr/share/man/man1/gst-{inspect,launch,stats,typefind}-1.0.1

    usr/share/bash-completion/completions/gst-{inspect,launch}-1.0
    usr/share/bash-completion/helpers/gst

    usr/share/gdb/auto-load/usr/lib/libgstreamer-1.0.so*.py
    usr/share/gstreamer-1.0/gdb/glib_gobject_helper.py
    usr/share/gstreamer-1.0/gdb/gst_gdb.py

    usr/share/aclocal/gst-element-check-1.0.m4
    usr/share/cmake/FindGStreamer.cmake
  ); _install
}

package_gst-plugins-bad-libs-qti-oss() {
  pkgdesc+=" - bad"
  depends=(
    "gst-plugins-base-libs-qti-oss=$pkgver-$pkgrel"
    "gstreamer-qti-oss=$pkgver-$pkgrel"
    glib2
    glibc
    libdrm
    libgcc
    libglvnd
    libgudev
    libnice
    libstdc++
    libusb
    libva
    libx11
    libxcb
    libxkbcommon
    libxkbcommon-x11
    mesa
    orc
    vulkan-icd-loader
    wayland
    vmaf
    zlib
  )

  provides=("gst-plugins-bad-libs=$pkgver-$pkgrel")
  conflicts=('gst-plugins-bad-libs')

  cd root; local files=(
    usr/include/gstreamer-1.0/gst/audio/{audio-bad-prelude,gstnonstreamaudiodecoder,gstplanaraudioadapter}.h
    usr/include/gstreamer-1.0/gst/{analytics,basecamerabinsrc,codecparsers,cuda,insertbin,interfaces,isoff,mpegts,mse,play,player,sctp,transcoder,uridownloader,va,vulkan,wayland,webrtc}
    usr/lib/libgst{adaptivedemux,analytics,badaudio,basecamerabinsrc,codecparsers,codecs,cuda,dxva,insertbin,isoff,mpegts,mse}-1.0.so*
    usr/lib/libgst{photography,play,player,sctp,transcoder,uridownloader,va,vulkan,wayland,webrtc,webrtcnice}-1.0.so*
    usr/lib/pkgconfig/gstreamer-{analytics,bad-audio,codecparsers,cuda,insertbin,mpegts,mse,photography,play,player,sctp,transcoder,vulkan{,-wayland,-xcb},va,wayland,webrtc{,-nice}}-1.0.pc
    usr/lib/girepository-1.0/{CudaGst,Gst{Analytics,BadAudio,Codecs,Cuda,Dxva,InsertBin,Mpegts,Mse,Play,Player,Transcoder,Va,Vulkan{,Wayland,XCB},WebRTC}}-1.0.typelib
    usr/share/gir-1.0/{CudaGst,Gst{Analytics,BadAudio,Codecs,Cuda,Dxva,InsertBin,Mpegts,Mse,Play,Player,Transcoder,Va,Vulkan{,Wayland,XCB},WebRTC}}-1.0.gir

    usr/lib/pkgconfig/gstreamer-plugins-bad-1.0.pc
    usr/lib/gstreamer-1.0/libgstaccurip.so
    usr/lib/gstreamer-1.0/libgstadpcmdec.so
    usr/lib/gstreamer-1.0/libgstadpcmenc.so
    usr/lib/gstreamer-1.0/libgstaiff.so
    usr/lib/gstreamer-1.0/libgstasfmux.so
    usr/lib/gstreamer-1.0/libgstaudiobuffersplit.so
    usr/lib/gstreamer-1.0/libgstaudiofxbad.so
    usr/lib/gstreamer-1.0/libgstaudiolatency.so
    usr/lib/gstreamer-1.0/libgstaudiomixmatrix.so
    usr/lib/gstreamer-1.0/libgstaudiovisualizers.so
    usr/lib/gstreamer-1.0/libgstautoconvert.so
    usr/lib/gstreamer-1.0/libgstbayer.so
    usr/lib/gstreamer-1.0/libgstbluez.so
    usr/lib/gstreamer-1.0/libgstcamerabin.so
    usr/lib/gstreamer-1.0/libgstcodecalpha.so
    usr/lib/gstreamer-1.0/libgstcodectimestamper.so
    usr/lib/gstreamer-1.0/libgstcoloreffects.so
    usr/lib/gstreamer-1.0/libgstdebugutilsbad.so
    usr/lib/gstreamer-1.0/libgstdecklink.so
    usr/lib/gstreamer-1.0/libgstdvb.so
    usr/lib/gstreamer-1.0/libgstdvbsubenc.so
    usr/lib/gstreamer-1.0/libgstdvbsuboverlay.so
    usr/lib/gstreamer-1.0/libgstdvdspu.so
    usr/lib/gstreamer-1.0/libgstfaceoverlay.so
    usr/lib/gstreamer-1.0/libgstfbdevsink.so
    usr/lib/gstreamer-1.0/libgstfestival.so
    usr/lib/gstreamer-1.0/libgstfieldanalysis.so
    usr/lib/gstreamer-1.0/libgstfreeverb.so
    usr/lib/gstreamer-1.0/libgstfrei0r.so
    usr/lib/gstreamer-1.0/libgstgaudieffects.so
    usr/lib/gstreamer-1.0/libgstgdp.so
    usr/lib/gstreamer-1.0/libgstgeometrictransform.so
    usr/lib/gstreamer-1.0/libgstid3tag.so
    usr/lib/gstreamer-1.0/libgstinsertbin.so
    usr/lib/gstreamer-1.0/libgstinter.so
    usr/lib/gstreamer-1.0/libgstinterlace.so
    usr/lib/gstreamer-1.0/libgstipcpipeline.so
    usr/lib/gstreamer-1.0/libgstivfparse.so
    usr/lib/gstreamer-1.0/libgstivtc.so
    usr/lib/gstreamer-1.0/libgstjp2kdecimator.so
    usr/lib/gstreamer-1.0/libgstjpegformat.so
    usr/lib/gstreamer-1.0/libgstkms.so
    usr/lib/gstreamer-1.0/libgstlegacyrawparse.so
    usr/lib/gstreamer-1.0/libgstmidi.so
    usr/lib/gstreamer-1.0/libgstmpegpsdemux.so
    usr/lib/gstreamer-1.0/libgstmpegpsmux.so
    usr/lib/gstreamer-1.0/libgstmpegtsdemux.so
    usr/lib/gstreamer-1.0/libgstmpegtsmux.so
    usr/lib/gstreamer-1.0/libgstmse.so
    usr/lib/gstreamer-1.0/libgstmxf.so
    usr/lib/gstreamer-1.0/libgstnetsim.so
    usr/lib/gstreamer-1.0/libgstnvcodec.so
    usr/lib/gstreamer-1.0/libgstpcapparse.so
    usr/lib/gstreamer-1.0/libgstpnm.so
    usr/lib/gstreamer-1.0/libgstproxy.so
    usr/lib/gstreamer-1.0/libgstremovesilence.so
    usr/lib/gstreamer-1.0/libgstrfbsrc.so
    usr/lib/gstreamer-1.0/libgstrist.so
    usr/lib/gstreamer-1.0/libgstrtmp2.so
    usr/lib/gstreamer-1.0/libgstrtpmanagerbad.so
    usr/lib/gstreamer-1.0/libgstrtponvif.so
    usr/lib/gstreamer-1.0/libgstsdpelem.so
    usr/lib/gstreamer-1.0/libgstsegmentclip.so
    usr/lib/gstreamer-1.0/libgstshm.so
    usr/lib/gstreamer-1.0/libgstsiren.so
    usr/lib/gstreamer-1.0/libgstsmooth.so
    usr/lib/gstreamer-1.0/libgstspeed.so
    usr/lib/gstreamer-1.0/libgstsubenc.so
    usr/lib/gstreamer-1.0/libgstswitchbin.so
    usr/lib/gstreamer-1.0/libgsttensordecoders.so
    usr/lib/gstreamer-1.0/libgsttranscode.so
    usr/lib/gstreamer-1.0/libgstunixfd.so
    usr/lib/gstreamer-1.0/libgstuvcgadget.so
    usr/lib/gstreamer-1.0/libgstuvch264.so
    usr/lib/gstreamer-1.0/libgstv4l2codecs.so
    usr/lib/gstreamer-1.0/libgstvideofiltersbad.so
    usr/lib/gstreamer-1.0/libgstvideoframe_audiolevel.so
    usr/lib/gstreamer-1.0/libgstvideoparsersbad.so
    usr/lib/gstreamer-1.0/libgstvideosignal.so
    usr/lib/gstreamer-1.0/libgstvmaf.so
    usr/lib/gstreamer-1.0/libgstvmnc.so
    usr/lib/gstreamer-1.0/libgstvulkan.so
    usr/lib/gstreamer-1.0/libgstwaylandsink.so

    usr/share/gstreamer-1.0/encoding-profiles
    usr/share/gstreamer-1.0/presets/GstFreeverb.prs

    usr/share/locale/*/LC_MESSAGES/gst-plugins-bad-1.0.mo

    usr/bin/gst-transcoder-1.0
  ); _install
}

package_gst-plugins-base-libs-qti-oss() {
  pkgdesc+=" - base"
  depends=(
    "gstreamer-qti-oss=$pkgver-$pkgrel"
    glib2
    glibc
    graphene
    iso-codes
    libdrm
    libglvnd
    libgudev
    libjpeg-turbo
    libpng
    libx11
    libxcb
    libxext
    libxi
    libxv
    mesa
    orc
    wayland
    zlib
  )

  provides=("gst-plugins-base-libs=$pkgver-$pkgrel")
  conflicts=('gst-plugins-base-libs')

  cd root; local files=(
    usr/include/gstreamer-1.0/gst/{allocators,app,audio,fft,gl,pbutils,riff,rtp,rtsp,sdp,tag,video}
    usr/lib/libgst{allocators,app,audio,fft,gl,pbutils,riff,rtp,rtsp,sdp,tag,video}-1.0.so*
    usr/lib/pkgconfig/gstreamer-{allocators,app,audio,fft,gl{,-egl,-prototypes,-wayland,-x11},pbutils,riff,rtp,rtsp,sdp,tag,video}-1.0.pc
    usr/lib/girepository-1.0/Gst{Allocators,App,Audio,GL{,EGL,Wayland,X11},Pbutils,Rtp,Rtsp,Sdp,Tag,Video}-1.0.typelib
    usr/share/gir-1.0/Gst{Allocators,App,Audio,GL{,EGL,Wayland,X11},Pbutils,Rtp,Rtsp,Sdp,Tag,Video}-1.0.gir

    usr/lib/pkgconfig/gstreamer-plugins-base-1.0.pc
    usr/lib/gstreamer-1.0/include/gst/gl/gstglconfig.h
    usr/lib/gstreamer-1.0/libgstadder.so
    usr/lib/gstreamer-1.0/libgstapp.so
    usr/lib/gstreamer-1.0/libgstaudioconvert.so
    usr/lib/gstreamer-1.0/libgstaudiomixer.so
    usr/lib/gstreamer-1.0/libgstaudiorate.so
    usr/lib/gstreamer-1.0/libgstaudioresample.so
    usr/lib/gstreamer-1.0/libgstaudiotestsrc.so
    usr/lib/gstreamer-1.0/libgstbasedebug.so
    usr/lib/gstreamer-1.0/libgstcompositor.so
    usr/lib/gstreamer-1.0/libgstdsd.so
    usr/lib/gstreamer-1.0/libgstencoding.so
    usr/lib/gstreamer-1.0/libgstgio.so
    usr/lib/gstreamer-1.0/libgstopengl.so
    usr/lib/gstreamer-1.0/libgstoverlaycomposition.so
    usr/lib/gstreamer-1.0/libgstpbtypes.so
    usr/lib/gstreamer-1.0/libgstplayback.so
    usr/lib/gstreamer-1.0/libgstrawparse.so
    usr/lib/gstreamer-1.0/libgstsubparse.so
    usr/lib/gstreamer-1.0/libgsttcp.so
    usr/lib/gstreamer-1.0/libgsttypefindfunctions.so
    usr/lib/gstreamer-1.0/libgstvideoconvertscale.so
    usr/lib/gstreamer-1.0/libgstvideorate.so
    usr/lib/gstreamer-1.0/libgstvideotestsrc.so
    usr/lib/gstreamer-1.0/libgstvolume.so
    usr/lib/gstreamer-1.0/libgstximagesink.so
    usr/lib/gstreamer-1.0/libgstxvimagesink.so

    usr/share/locale/*/LC_MESSAGES/gst-plugins-base-1.0.mo

    usr/bin/gst-{device-monitor,discoverer,play}-1.0
    usr/share/man/man1/gst-{device-monitor,discoverer,play}-1.0.1

    usr/share/gst-plugins-base
  ); _install
}

package_gst-plugins-base-qti-oss() {
  pkgdesc+=" - base plugins"
  depends=(
    "gst-plugins-base-libs-qti-oss=$pkgver-$pkgrel"
    "gstreamer-qti-oss=$pkgver-$pkgrel"
    alsa-lib
    cairo
    cdparanoia
    glib2
    glibc
    libgcc
    libogg
    libtheora
    libvorbis
    opus
    pango
  )

  provides=("gst-plugins-base=$pkgver-$pkgrel")
  conflicts=('gst-plugins-base')

  cd root; local files=(
    usr/lib/gstreamer-1.0/libgstalsa.so
    usr/lib/gstreamer-1.0/libgstcdparanoia.so
    usr/lib/gstreamer-1.0/libgstogg.so
    usr/lib/gstreamer-1.0/libgstopus.so
    usr/lib/gstreamer-1.0/libgstpango.so
    usr/lib/gstreamer-1.0/libgsttheora.so
    usr/lib/gstreamer-1.0/libgstvorbis.so
  ); _install
}

package_gst-plugins-good-qti-oss() {
  pkgdesc+=" - good plugins"
  depends=(
    "gst-plugins-base-libs-qti-oss=$pkgver-$pkgrel"
    "gstreamer-qti-oss=$pkgver-$pkgrel"
    aalib
    bzip2
    cairo
    flac
    gdk-pixbuf2
    glib2
    glibc
    lame
    libavc1394
    libcaca
    libdv
    libgcc
    libgudev
    libiec61883
    libjpeg-turbo
    libpng
    libpulse
    libraw1394
    libshout
    libsoup3
    libstdc++
    libvpx
    libx11
    libxdamage
    libxext
    libxfixes
    libxml2
    libxtst
    mpg123
    nettle
    opencore-amr
    orc
    speex
    taglib
    twolame
    v4l-utils
    wavpack
    zlib
  )
  optdepends=("jack: JACK backend")
  provides=("gst-plugins-good=$pkgver-$pkgrel")
  conflicts=('gst-plugins-good')

  cd root; local files=(
    usr/lib/gstreamer-1.0/libgst1394.so
    usr/lib/gstreamer-1.0/libgstaasink.so
    usr/lib/gstreamer-1.0/libgstadaptivedemux2.so
    usr/lib/gstreamer-1.0/libgstalaw.so
    usr/lib/gstreamer-1.0/libgstalpha.so
    usr/lib/gstreamer-1.0/libgstalphacolor.so
    usr/lib/gstreamer-1.0/libgstamrnb.so
    usr/lib/gstreamer-1.0/libgstamrwbdec.so
    usr/lib/gstreamer-1.0/libgstapetag.so
    usr/lib/gstreamer-1.0/libgstaudiofx.so
    usr/lib/gstreamer-1.0/libgstaudioparsers.so
    usr/lib/gstreamer-1.0/libgstauparse.so
    usr/lib/gstreamer-1.0/libgstautodetect.so
    usr/lib/gstreamer-1.0/libgstavi.so
    usr/lib/gstreamer-1.0/libgstcacasink.so
    usr/lib/gstreamer-1.0/libgstcairo.so
    usr/lib/gstreamer-1.0/libgstcutter.so
    usr/lib/gstreamer-1.0/libgstdebug.so
    usr/lib/gstreamer-1.0/libgstdeinterlace.so
    usr/lib/gstreamer-1.0/libgstdtmf.so
    usr/lib/gstreamer-1.0/libgstdv.so
    usr/lib/gstreamer-1.0/libgsteffectv.so
    usr/lib/gstreamer-1.0/libgstequalizer.so
    usr/lib/gstreamer-1.0/libgstflac.so
    usr/lib/gstreamer-1.0/libgstflv.so
    usr/lib/gstreamer-1.0/libgstflxdec.so
    usr/lib/gstreamer-1.0/libgstgdkpixbuf.so
    usr/lib/gstreamer-1.0/libgstgoom.so
    usr/lib/gstreamer-1.0/libgstgoom2k1.so
    usr/lib/gstreamer-1.0/libgsticydemux.so
    usr/lib/gstreamer-1.0/libgstid3demux.so
    usr/lib/gstreamer-1.0/libgstimagefreeze.so
    usr/lib/gstreamer-1.0/libgstinterleave.so
    usr/lib/gstreamer-1.0/libgstisomp4.so
    usr/lib/gstreamer-1.0/libgstjack.so
    usr/lib/gstreamer-1.0/libgstjpeg.so
    usr/lib/gstreamer-1.0/libgstlame.so
    usr/lib/gstreamer-1.0/libgstlevel.so
    usr/lib/gstreamer-1.0/libgstmatroska.so
    usr/lib/gstreamer-1.0/libgstmonoscope.so
    usr/lib/gstreamer-1.0/libgstmpg123.so
    usr/lib/gstreamer-1.0/libgstmulaw.so
    usr/lib/gstreamer-1.0/libgstmultifile.so
    usr/lib/gstreamer-1.0/libgstmultipart.so
    usr/lib/gstreamer-1.0/libgstnavigationtest.so
    usr/lib/gstreamer-1.0/libgstoss4.so
    usr/lib/gstreamer-1.0/libgstossaudio.so
    usr/lib/gstreamer-1.0/libgstpng.so
    usr/lib/gstreamer-1.0/libgstpulseaudio.so
    usr/lib/gstreamer-1.0/libgstreplaygain.so
    usr/lib/gstreamer-1.0/libgstrtp.so
    usr/lib/gstreamer-1.0/libgstrtpmanager.so
    usr/lib/gstreamer-1.0/libgstrtsp.so
    usr/lib/gstreamer-1.0/libgstshapewipe.so
    usr/lib/gstreamer-1.0/libgstshout2.so
    usr/lib/gstreamer-1.0/libgstsmpte.so
    usr/lib/gstreamer-1.0/libgstsoup.so
    usr/lib/gstreamer-1.0/libgstspectrum.so
    usr/lib/gstreamer-1.0/libgstspeex.so
    usr/lib/gstreamer-1.0/libgsttaglib.so
    usr/lib/gstreamer-1.0/libgsttwolame.so
    usr/lib/gstreamer-1.0/libgstudp.so
    usr/lib/gstreamer-1.0/libgstvideo4linux2.so
    usr/lib/gstreamer-1.0/libgstvideobox.so
    usr/lib/gstreamer-1.0/libgstvideocrop.so
    usr/lib/gstreamer-1.0/libgstvideofilter.so
    usr/lib/gstreamer-1.0/libgstvideomixer.so
    usr/lib/gstreamer-1.0/libgstvpx.so
    usr/lib/gstreamer-1.0/libgstwavenc.so
    usr/lib/gstreamer-1.0/libgstwavpack.so
    usr/lib/gstreamer-1.0/libgstwavparse.so
    usr/lib/gstreamer-1.0/libgstximagesrc.so
    usr/lib/gstreamer-1.0/libgstxingmux.so
    usr/lib/gstreamer-1.0/libgsty4m.so

    usr/share/gstreamer-1.0/presets/GstIirEqualizer{3,10}Bands.prs
    usr/share/gstreamer-1.0/presets/GstQTMux.prs
    usr/share/gstreamer-1.0/presets/Gst{Amrnb,VP8}Enc.prs

    usr/share/locale/*/LC_MESSAGES/gst-plugins-good-1.0.mo
  ); _install
}

package_gst-plugins-bad-qti-oss() {
  pkgdesc+=" - bad plugins"
  depends=(
    "gst-plugins-bad-libs-qti-oss=$pkgver-$pkgrel"
    "gst-plugins-base-libs-qti-oss=$pkgver-$pkgrel"
    "gstreamer-qti-oss=$pkgver-$pkgrel"
    aom
    bzip2
    cairo
    chromaprint
    curl
    faac
    faad2
    fluidsynth
    glib2
    glibc
    gsm
    imath
    json-glib
    lcms2
    libass
    libavtp
    libbs2b
    libdc1394
    libdca
    libde265
    libdvdnav
    libdvdread
    libfdk-aac
    libfreeaptx
    libgcc
    libgme
    liblc3
    libldac
    liblrdf
    libltc
    libmicrodns
    libmodplug
    libmpcdec
    libopenmpt
    librsvg
    libsndfile
    libsrtp
    libstdc++
    libwebp
    libxml2
    lilv
    mjpegtools
    neon
    nettle
    openal
    openexr
    openh264
    openjpeg2
    openssl
    opus
    pango
    qrencode
    rtmpdump
    sbc
    soundtouch
    spandsp
    srt
    svt-av1
    svt-hevc
    webrtc-audio-processing-1
    wildmidi
    x265
    zbar
    zvbi
    zxing-cpp
  )
  optdepends=(
    'gst-plugin-gtk: gtk plugin'
    'gst-plugin-hip: hip plugin and library'
    'gst-plugin-msdk: msdk plugin'
    'gst-plugin-onnx: onnx plugin'
    'gst-plugin-opencv: opencv plugin and library'
    'gst-plugin-qml6: qml6 plugin'
    'gst-plugin-qmlgl: qmlgl plugin'
    'gst-plugin-qsv: qsv plugin'
    'gst-plugin-va: va plugin'
    'gst-plugin-wpe: wpe plugin'
  )
  provides=("gst-plugins-bad=$pkgver-$pkgrel")
  conflicts=('gst-plugins-bad')

  cd root; local files=(
    usr/lib/gstreamer-1.0/libgstaes.so
    usr/lib/gstreamer-1.0/libgstanalyticsoverlay.so
    usr/lib/gstreamer-1.0/libgstaom.so
    usr/lib/gstreamer-1.0/libgstassrender.so
    usr/lib/gstreamer-1.0/libgstavtp.so
    usr/lib/gstreamer-1.0/libgstbs2b.so
    usr/lib/gstreamer-1.0/libgstbz2.so
    usr/lib/gstreamer-1.0/libgstchromaprint.so
    usr/lib/gstreamer-1.0/libgstclosedcaption.so
    usr/lib/gstreamer-1.0/libgstcodec2json.so
    usr/lib/gstreamer-1.0/libgstcolormanagement.so
    usr/lib/gstreamer-1.0/libgstcurl.so
    usr/lib/gstreamer-1.0/libgstdash.so
    usr/lib/gstreamer-1.0/libgstdc1394.so
    usr/lib/gstreamer-1.0/libgstde265.so
    usr/lib/gstreamer-1.0/libgstdtls.so
    usr/lib/gstreamer-1.0/libgstdtsdec.so
    usr/lib/gstreamer-1.0/libgstfaac.so
    usr/lib/gstreamer-1.0/libgstfaad.so
    usr/lib/gstreamer-1.0/libgstfdkaac.so
    usr/lib/gstreamer-1.0/libgstfluidsynthmidi.so
    usr/lib/gstreamer-1.0/libgstgme.so
    usr/lib/gstreamer-1.0/libgstgsm.so
    usr/lib/gstreamer-1.0/libgsthls.so
    usr/lib/gstreamer-1.0/libgstladspa.so
    usr/lib/gstreamer-1.0/libgstlc3.so
    usr/lib/gstreamer-1.0/libgstldac.so
    usr/lib/gstreamer-1.0/libgstlv2.so
    usr/lib/gstreamer-1.0/libgstmicrodns.so
    usr/lib/gstreamer-1.0/libgstmodplug.so
    usr/lib/gstreamer-1.0/libgstmpeg2enc.so
    usr/lib/gstreamer-1.0/libgstmplex.so
    usr/lib/gstreamer-1.0/libgstmusepack.so
    usr/lib/gstreamer-1.0/libgstneonhttpsrc.so
    usr/lib/gstreamer-1.0/libgstopenal.so
    usr/lib/gstreamer-1.0/libgstopenaptx.so
    usr/lib/gstreamer-1.0/libgstopenexr.so
    usr/lib/gstreamer-1.0/libgstopenh264.so
    usr/lib/gstreamer-1.0/libgstopenjpeg.so
    usr/lib/gstreamer-1.0/libgstopenmpt.so
    usr/lib/gstreamer-1.0/libgstopusparse.so
    usr/lib/gstreamer-1.0/libgstqroverlay.so
    usr/lib/gstreamer-1.0/libgstresindvd.so
    usr/lib/gstreamer-1.0/libgstrsvg.so
    usr/lib/gstreamer-1.0/libgstrtmp.so
    usr/lib/gstreamer-1.0/libgstsbc.so
    usr/lib/gstreamer-1.0/libgstsctp.so
    usr/lib/gstreamer-1.0/libgstsmoothstreaming.so
    usr/lib/gstreamer-1.0/libgstsndfile.so
    usr/lib/gstreamer-1.0/libgstsoundtouch.so
    usr/lib/gstreamer-1.0/libgstspandsp.so
    usr/lib/gstreamer-1.0/libgstsrt.so
    usr/lib/gstreamer-1.0/libgstsrtp.so
    usr/lib/gstreamer-1.0/libgstsvtav1.so
    usr/lib/gstreamer-1.0/libgstteletext.so
    usr/lib/gstreamer-1.0/libgsttimecode.so
    usr/lib/gstreamer-1.0/libgstttmlsubs.so
    usr/lib/gstreamer-1.0/libgstwebp.so
    usr/lib/gstreamer-1.0/libgstwebrtc.so
    usr/lib/gstreamer-1.0/libgstwebrtcdsp.so
    usr/lib/gstreamer-1.0/libgstwildmidi.so
    usr/lib/gstreamer-1.0/libgstx265.so
    usr/lib/gstreamer-1.0/libgstzbar.so
    usr/lib/gstreamer-1.0/libgstzxing.so
  ); _install
}

package_gst-plugins-ugly-qti-oss() {
  pkgdesc+=" - ugly plugins"
  depends=(
    "gst-plugins-base-libs-qti-oss=$pkgver-$pkgrel"
    "gstreamer-qti-oss=$pkgver-$pkgrel"
    a52dec
    glib2
    glibc
    libcdio
    libdvdread
    libmpeg2
    x264
  )
  provides=("gst-plugins-ugly=$pkgver-$pkgrel")
  conflicts=('gst-plugins-ugly')

  cd root; local files=(
    usr/lib/gstreamer-1.0/libgsta52dec.so
    usr/lib/gstreamer-1.0/libgstasf.so
    usr/lib/gstreamer-1.0/libgstcdio.so
    usr/lib/gstreamer-1.0/libgstdvdlpcmdec.so
    usr/lib/gstreamer-1.0/libgstdvdread.so
    usr/lib/gstreamer-1.0/libgstdvdsub.so
    usr/lib/gstreamer-1.0/libgstmpeg2dec.so
    usr/lib/gstreamer-1.0/libgstrealmedia.so
    usr/lib/gstreamer-1.0/libgstx264.so

    usr/share/gstreamer-1.0/presets/GstX264Enc.prs

    usr/share/locale/*/LC_MESSAGES/gst-plugins-ugly-1.0.mo
  ); _install
}

package_gst-libav-qti-oss() {
  pkgdesc+=" - libav plugin"
  depends=(
    "gst-plugins-base-libs-qti-oss=$pkgver-$pkgrel"
    "gstreamer-qti-oss=$pkgver-$pkgrel"
    ffmpeg
    glib2
    glibc
  )
  provides=("gst-ffmpeg=$pkgver-$pkgrel" "gst-libav=$pkgver-$pkgrel")
  conflicts=('gst-ffmpeg' 'gst-libav')

  cd root; local files=(
    usr/lib/gstreamer-1.0/libgstlibav.so
  ); _install
}

package_gst-plugin-gtk-qti-oss() {
  pkgdesc+=" - gtk plugin"
  depends=(
    "gst-plugins-bad-libs-qti-oss=$pkgver-$pkgrel"
    "gst-plugins-base-libs-qti-oss=$pkgver-$pkgrel"
    "gstreamer-qti-oss=$pkgver-$pkgrel"
    cairo
    glib2
    glibc
    gtk3
    wayland
  )
  provides=("gst-plugin-gtk=$pkgver-$pkgrel")
  conflicts=('gst-plugin-gtk')

  cd root; local files=(
    usr/lib/gstreamer-1.0/libgstgtk.so
    usr/lib/gstreamer-1.0/libgstgtkwayland.so
  ); _install
}

package_gst-plugin-hip-qti-oss() {
  pkgdesc+=" - hip plugin and library"
  depends=(
    "gst-plugins-bad-libs-qti-oss=$pkgver-$pkgrel"
    "gst-plugins-base-libs-qti-oss=$pkgver-$pkgrel"
    "gstreamer-qti-oss=$pkgver-$pkgrel"
    glib2
    glibc
    libdrm
    libgcc
    libgudev
    libstdc++
    libx11
    mesa
    orc
    wayland
  )

  provides=("gst-plugin-hip=$pkgver-$pkgrel")
  conflicts=('gst-plugin-hip')

  cd root; local files=(
    usr/include/gstreamer-1.0/gst/hip
    usr/lib/libgsthip.so*
    usr/lib/pkgconfig/gstreamer-hip{,-gl}-1.0.pc
    usr/lib/girepository-1.0/GstHip{,GL}-1.0.typelib
    usr/share/gir-1.0/GstHip{,GL}-1.0.gir

    usr/lib/gstreamer-1.0/libgsthip.so
  ); _install
}

package_gst-plugin-msdk-qti-oss() {
  pkgdesc+=" - msdk plugin"
  depends=(
    "gst-plugins-bad-libs-qti-oss=$pkgver-$pkgrel"
    "gst-plugins-base-libs-qti-oss=$pkgver-$pkgrel"
    "gstreamer-qti-oss=$pkgver-$pkgrel"
    glib2
    glibc
    libdrm
    libgudev
    libva
    libvpl
  )

  provides=("gst-plugin-msdk=$pkgver-$pkgrel")
  conflicts=('gst-plugin-msdk')

  cd root; local files=(
    usr/lib/gstreamer-1.0/libgstmsdk.so
  ); _install
}

package_gst-plugin-onnx-qti-oss() {
  pkgdesc+=" - onnx plugin"
  depends=(
    "gst-plugins-bad-libs-qti-oss=$pkgver-$pkgrel"
    "gst-plugins-base-libs-qti-oss=$pkgver-$pkgrel"
    "gstreamer-qti-oss=$pkgver-$pkgrel"
    glib2
    glibc
    onnxruntime
  )

  provides=("gst-plugin-onnx=$pkgver-$pkgrel")
  conflicts=('gst-plugin-onnx')

  cd root; local files=(
    usr/lib/gstreamer-1.0/libgstonnx.so
  ); _install
}

package_gst-plugin-opencv-qti-oss() {
  pkgdesc+=" - opencv plugin and library"
  depends=(
    "gst-plugins-base-libs-qti-oss=$pkgver-$pkgrel"
    "gstreamer-qti-oss=$pkgver-$pkgrel"
    glib2
    glibc
    libgcc
    libstdc++
    opencv
  )

  provides=("gst-plugin-opencv=$pkgver-$pkgrel")
  conflicts=('gst-plugin-opencv')

  cd root; local files=(
    usr/include/gstreamer-1.0/gst/opencv
    usr/lib/libgstopencv-1.0.so*

    usr/lib/gstreamer-1.0/libgstopencv.so
  ); _install
}

package_gst-plugin-qml6-qti-oss() {
  pkgdesc+=" - qml6 plugin"
  depends=(
    "gst-plugins-base-libs-qti-oss=$pkgver-$pkgrel"
    "gstreamer-qti-oss=$pkgver-$pkgrel"
    glib2
    glibc
    libgcc
    libglvnd
    libstdc++
    qt6-base
    qt6-declarative
  )

  provides=("gst-plugin-qml6=$pkgver-$pkgrel")
  conflicts=('gst-plugin-qml6')

  cd root; local files=(
    usr/lib/gstreamer-1.0/libgstqml6.so
  ); _install
}

package_gst-plugin-qmlgl-qti-oss() {
  pkgdesc+=" - qmlgl plugin"
  depends=(
    "gst-plugins-base-libs-qti-oss=$pkgver-$pkgrel"
    "gstreamer-qti-oss=$pkgver-$pkgrel"
    glib2
    glibc
    libgcc
    libglvnd
    libstdc++
    qt5-base
    qt5-declarative
    qt5-wayland
    qt5-x11extras
  )

  provides=("gst-plugin-qmlgl=$pkgver-$pkgrel")
  conflicts=('gst-plugin-qmlgl')

  cd root; local files=(
    usr/lib/gstreamer-1.0/libgstqmlgl.so
  ); _install
}

package_gst-plugin-qsv-qti-oss() {
  pkgdesc+=" - qsv plugin"
  depends=(
    "gst-plugins-bad-libs-qti-oss=$pkgver-$pkgrel"
    "gst-plugins-base-libs-qti-oss=$pkgver-$pkgrel"
    "gstreamer-qti-oss=$pkgver-$pkgrel"
    glib2
    glibc
    libgcc
    libstdc++
  )
  optdepends=(
    "intel-media-sdk: runtime for legacy Intel GPUs"
    "onevpl-intel-gpu: runtime for Tiger Lake and newer GPUs"
  )

  provides=("gst-plugin-qsv=$pkgver-$pkgrel")
  conflicts=('gst-plugin-qsv')

  cd root; local files=(
    usr/lib/gstreamer-1.0/libgstqsv.so
  ); _install
}

package_gst-plugin-va-qti-oss() {
  pkgdesc+=" - va plugin"
  depends=(
    "gst-plugins-bad-libs-qti-oss=$pkgver-$pkgrel"
    "gst-plugins-base-libs-qti-oss=$pkgver-$pkgrel"
    "gstreamer-qti-oss=$pkgver-$pkgrel"
    glib2
    glibc
    libgudev
    libva
  )
  replaces=('gstreamer-vaapi<=1.26.10-5')

  provides=("gst-plugin-va=$pkgver-$pkgrel")
  conflicts=('gst-plugin-va')

  cd root; local files=(
    usr/lib/gstreamer-1.0/libgstva.so
  ); _install
}

package_gst-plugin-wpe-qti-oss() {
  pkgdesc+=" - wpe plugin"
  depends=(
    "gst-plugins-base-libs-qti-oss=$pkgver-$pkgrel"
    "gstreamer-qti-oss=$pkgver-$pkgrel"
    glib2
    glibc
    libgcc
    libstdc++
    libwpe
    libxkbcommon
    wayland
    wpebackend-fdo
    wpewebkit
  )

  provides=("gst-plugin-wpe=$pkgver-$pkgrel")
  conflicts=('gst-plugin-wpe')

  cd root; local files=(
    usr/lib/gstreamer-1.0/libgstwpe.so
    usr/lib/gst-plugins-bad/wpe-extension/libgstwpeextension.so
  ); _install
}

package_gst-plugin-wpe2-qti-oss() {
  pkgdesc+=" - wpe2 plugin"
  depends=(
    "gst-plugins-base-libs-qti-oss=$pkgver-$pkgrel"
    "gstreamer-qti-oss=$pkgver-$pkgrel"
    glib2
    glibc
    libgcc
    libglvnd
    libstdc++
    libxkbcommon
    wpewebkit
  )

  provides=("gst-plugin-wpe2=$pkgver-$pkgrel")
  conflicts=('gst-plugin-wpe2')

  cd root; local files=(
    usr/lib/gstreamer-1.0/libgstwpe2.so
  ); _install
}

package_gst-devtools-libs-qti-oss() {
  pkgdesc+=" - development and debugging libraries"
  depends=(
    "gst-plugins-base-libs-qti-oss=$pkgver-$pkgrel"
    "gstreamer-qti-oss=$pkgver-$pkgrel"
    glib2
    glibc
    json-glib
    orc
    zlib
  )

  provides=("gst-devtools-libs=$pkgver-$pkgrel")
  conflicts=('gst-devtools-libs')

  cd root; local files=(
    usr/include/gstreamer-1.0/gst/validate
    usr/lib/libgstvalidate-*
    usr/lib/pkgconfig/gstreamer-validate-1.0.pc
    usr/lib/girepository-1.0/GstValidate-1.0.typelib
    usr/share/gir-1.0/GstValidate-1.0.gir
  ); _install
}

package_gst-devtools-qti-oss() {
  pkgdesc+=" - development and debugging tools"
  depends=(
    "gst-devtools-libs-qti-oss=$pkgver-$pkgrel"
    "gst-plugins-bad-libs-qti-oss=$pkgver-$pkgrel"
    "gst-plugins-base-libs-qti-oss=$pkgver-$pkgrel"
    "gst-rtsp-server-qti-oss=$pkgver-$pkgrel"
    "gstreamer-qti-oss=$pkgver-$pkgrel"
    cairo
    glib2
    glibc
    gtk3
    hicolor-icon-theme
    json-glib
    libgcc
    python
    python-cairo
    python-commonmark
    python-gobject
    python-lxml
  )

  provides=("gst-devtools=$pkgver-$pkgrel")
  conflicts=('gst-devtools')

  cd root; local files=(
    usr/bin/gst-validate-*
    usr/lib/gst-validate-launcher
    usr/lib/gstreamer-1.0/libgstvalidatetracer.so
    usr/lib/gstreamer-1.0/validate
    usr/share/gstreamer-1.0/validate

    usr/bin/gst-debug-viewer
    usr/lib/python*/site-packages/GstDebugViewer
    usr/share/applications/org.freedesktop.GstDebugViewer.desktop
    usr/share/gst-debug-viewer
    usr/share/icons/hicolor/*/apps/gst-debug-viewer.*
    usr/share/metainfo/org.freedesktop.GstDebugViewer.appdata.xml

    usr/bin/gst-dots-viewer
  ); _install
}

package_gst-rtsp-server-qti-oss() {
  pkgdesc+=" - rtsp server"
  depends=(
    "gst-plugins-base-libs-qti-oss=$pkgver-$pkgrel"
    "gstreamer-qti-oss=$pkgver-$pkgrel"
    glib2
    glibc
    orc
    zlib
  )

  provides=("gst-rtsp-server=$pkgver-$pkgrel")
  conflicts=('gst-rtsp-server')

  cd root; local files=(
    usr/include/gstreamer-1.0/gst/rtsp-server
    usr/lib/libgstrtspserver-1.0.so*
    usr/lib/pkgconfig/gstreamer-rtsp-server-1.0.pc
    usr/lib/girepository-1.0/GstRtspServer-1.0.typelib
    usr/share/gir-1.0/GstRtspServer-1.0.gir

    usr/lib/gstreamer-1.0/libgstrtspclientsink.so
  ); _install
}

package_gst-editing-services-qti-oss() {
  pkgdesc+=" - editing services"
  depends=(
    "gst-devtools-libs-qti-oss=$pkgver-$pkgrel"
    "gst-plugins-base-libs-qti-oss=$pkgver-$pkgrel"
    "gst-python-qti-oss=$pkgver-$pkgrel"
    "gstreamer-qti-oss=$pkgver-$pkgrel"
    glib2
    glibc
    json-glib
    libxml2
    orc
    python
    python-gobject
    zlib
  )
  optdepends=("opentimelineio: Support for the OpenTimelineIO format")

  provides=("gst-editing-services=$pkgver-$pkgrel")
  conflicts=('gst-editing-services')

  cd root; local files=(
    usr/include/gstreamer-1.0/ges
    usr/lib/libges-1.0.so*
    usr/lib/pkgconfig/gst-editing-services-1.0.pc
    usr/lib/girepository-1.0/GES-1.0.typelib
    usr/share/gir-1.0/GES-1.0.gir

    usr/lib/gstreamer-1.0/libgstges.so
    usr/lib/gstreamer-1.0/libgstnle.so
    usr/lib/gstreamer-1.0/python/gesotioformatter.py

    usr/lib/python*/site-packages/gi/overrides/GES.py
    usr/lib/python*/site-packages/gi/overrides/__pycache__/GES.*.pyc

    usr/bin/ges-launch-1.0
    usr/share/man/man1/ges-launch-1.0.1

    usr/share/bash-completion/completions/ges-launch-1.0
  ); _install
}

package_gst-python-qti-oss() {
  pkgdesc+=" - python plugin"
  depends=(
    "gst-plugins-base-libs-qti-oss=$pkgver-$pkgrel"
    "gstreamer-qti-oss=$pkgver-$pkgrel"
    glib2
    glibc
    python
    python-gobject
    python-typing_extensions
  )
  optdepends=("gst-plugins-bad-libs-qti-oss: GstAnalytics support")

  provides=("gst-python=$pkgver-$pkgrel")
  conflicts=('gst-python')

  cd root; local files=(
    usr/lib/gstreamer-1.0/libgstpython.so
    usr/lib/python*/site-packages/gi/overrides
  ); _install
}

# vim:set sw=2 sts=-1 et:
