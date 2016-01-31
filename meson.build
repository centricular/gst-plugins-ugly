project('gst-plugins-ugly', 'c',
  version : '1.7.1.1',
  meson_version : '>= 0.27.0',
  default_options : [ 'warning_level=1',
                      'c_std=gnu99',
                      'buildtype=debugoptimized' ])

gst_version = meson.project_version()
version_arr = gst_version.split('.')
gst_version_major = version_arr[0]
gst_version_minor = version_arr[1]
gst_version_micro = version_arr[2]
if version_arr.length() == 4
  gst_version_nano = version_arr[3]
else
  gst_version_nano = 0
endif

glib_req = '>= 2.40.0'
gst_req = '>= @0@.@1@.0'.format(gst_version_major, gst_version_minor)

api_version = '1.0'

plugins_install_dir = '@0@/gstreamer-1.0'.format(get_option('libdir'))

cc = meson.get_compiler('c')
cdata = configuration_data()
check_headers = [
  ['HAVE_DLFCN_H', 'dlfcn.h'],
  ['HAVE_INTTYPES_H', 'inttypes.h'],
  ['HAVE_MALLOC_H', 'malloc.h'],
  ['HAVE_MEMORY_H', 'memory.h'],
  ['HAVE_STDINT_H', 'stdint.h'],
  ['HAVE_STDLIB_H', 'stdlib.h'],
  ['HAVE_STRINGS_H', 'strings.h'],
  ['HAVE_STRING_H', 'string.h'],
  ['HAVE_SYS_STAT_H', 'sys/stat.h'],
  ['HAVE_SYS_TYPES_H', 'sys/types.h'],
  ['HAVE_UNISTD_H', 'unistd.h'],
  ['HAVE_WINSOCK2_H', 'winsock2.h'],
]

foreach h : check_headers
  if cc.has_header(h.get(1))
    cdata.set(h.get(0), 1)
  endif
endforeach

check_functions = [
# check token HAVE_A52DEC
# check token HAVE_AMRNB
# check token HAVE_AMRWB
# check token HAVE_CDIO
# check token HAVE_CFLOCALECOPYCURRENT
# check token HAVE_CFPREFERENCESCOPYAPPVALUE
# check token HAVE_CPU_ALPHA
# check token HAVE_CPU_ARM
# check token HAVE_CPU_CRIS
# check token HAVE_CPU_CRISV32
# check token HAVE_CPU_HPPA
# check token HAVE_CPU_I386
# check token HAVE_CPU_IA64
# check token HAVE_CPU_M68K
# check token HAVE_CPU_MIPS
# check token HAVE_CPU_PPC
# check token HAVE_CPU_PPC64
# check token HAVE_CPU_S390
# check token HAVE_CPU_SPARC
# check token HAVE_CPU_X86_64
  ['HAVE_DCGETTEXT', 'dcgettext', '#include<libintl.h>'],
# check token HAVE_DOWHILE_MACROS
# check token HAVE_DVDREAD
# check token HAVE_EXPERIMENTAL
# check token HAVE_EXTERNAL
# check token HAVE_FUNC
# check token HAVE_FUNCTION
# check token HAVE_GETTEXT
# check token HAVE_ICONV
# check token HAVE_LAME
# check token HAVE_MAD
# check token HAVE_MPEG2DEC
# check token HAVE_ORC
# check token HAVE_PRETTY_FUNCTION
# check token HAVE_RDTSC
# check token HAVE_SIDPLAY
# check token HAVE_TWOLAME
# check token HAVE_VALGRIND
]

foreach f : check_functions
  if cc.has_function(f.get(1), prefix : f.get(2))
    cdata.set(f.get(0), 1)
  endif
endforeach

cdata.set('SIZEOF_CHAR', cc.sizeof('char'))
cdata.set('SIZEOF_INT', cc.sizeof('int'))
cdata.set('SIZEOF_LONG', cc.sizeof('long'))
cdata.set('SIZEOF_SHORT', cc.sizeof('short'))
cdata.set('SIZEOF_VOIDP', cc.sizeof('void*'))

cdata.set('VERSION', '"@0@"'.format(gst_version))
cdata.set('PACKAGE', '"gst-plugins-ugly"')
cdata.set('GETTEXT_PACKAGE', '"gst-plugins-ugly-1.0"')
cdata.set('GST_PACKAGE_NAME', '"GStreamer Ugly Plug-ins"')
cdata.set('GST_PACKAGE_ORIGIN', '"Unknown package origin"')
cdata.set('GST_LICENSE', '"LGPL"')

# Mandatory GST deps
gst_dep = dependency('gstreamer-1.0', version : gst_req)
gstapp_dep = dependency('gstreamer-app-1.0', version : gst_req)
gstvideo_dep = dependency('gstreamer-video-1.0', version : gst_req)
gstpbutils_dep = dependency('gstreamer-pbutils-1.0', version : gst_req)
gsttag_dep = dependency('gstreamer-tag-1.0', version : gst_req)
gstfft_dep = dependency('gstreamer-fft-1.0', version : gst_req)
gstaudio_dep = dependency('gstreamer-audio-1.0', version : gst_req)
gstbase_dep = dependency('gstreamer-base-1.0', version : gst_req)
gstriff_dep = dependency('gstreamer-riff-1.0', version : gst_req)
gstrtp_dep = dependency('gstreamer-rtp-1.0', version : gst_req)
gstnet_dep = dependency('gstreamer-net-1.0', version : gst_req)
gstsdp_dep = dependency('gstreamer-sdp-1.0', version : gst_req)
gstrtsp_dep = dependency('gstreamer-rtsp-1.0', version : gst_req)
gstcheck_dep = dependency('gstreamer-check-1.0', version : gst_req)
gstcontroller_dep = dependency('gstreamer-controller-1.0', version : gst_req)

orc_dep = dependency('orc-0.4', version : '>= 0.4.16')
x264_dep = dependency('x264', required : false)
a52_dep = find_library('a52', required : false)
amrnb_dep = dependency('opencore-amrnb', version : '>= 0.1.3', required : false)
amrwb_dep = dependency('opencore-amrwb', version : '>= 0.1.3', required : false)
cdio_dep = dependency('libcdio', version : '>= 0.76', required : false)
dvdread_dep = dependency('dvdread', version : '>= 0.5.0', required : false)
lame_dep = find_library('mp3lame', required : false)
mad_dep = dependency('mad', version : '>= 0.15', required : false)
if not mad_dep.found() and cc.has_function('mad_decoder_finish', prefix : '#include <mad.h>')
  mad_dep = find_library('mad', required : false)
endif
mpeg2_dep = dependency('libmpeg2', version : '>= 0.4.0', required : false)
twolame_dep = dependency('twolame', version : '>= 0.3.10', required : false)

if orc_dep.found()
  cdata.set('HAVE_ORC', 1) # used by a52dec for cpu detection
endif

configure_file(input : 'config.h.meson',
  output : 'config.h',
  configuration : cdata)

ugly_args = [ '-DHAVE_CONFIG_H' ]
ugly_incs = include_directories('.', 'gst-libs')

subdir('gst')
subdir('ext')
