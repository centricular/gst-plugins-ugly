asf_sources = [
  'gstasfdemux.c',
  'gstasf.c',
  'asfheaders.c',
  'asfpacket.c',
  'gstrtpasfdepay.c',
  'gstrtspwms.c',
]

gstasf = library('gstasf',
  asf_sources,
  c_args : ugly_args,
  include_directories : ugly_incs,
  dependencies : [ gstbase_dep, gstrtp_dep, gstvideo_dep, gstaudio_dep, gsttag_dep, gstriff_dep, gstrtsp_dep ],
  install : true,
  install_dir : '@0@/gstreamer-1.0'.format(get_option('libdir')),
)
