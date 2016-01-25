x264_sources = [
  'gstx264enc.c',
]

gstx264 = library('gstx264',
  x264_sources,
  c_args : ugly_args,
  include_directories : ugly_incs,
  dependencies : [ x264_dep, gstbase_dep, gstvideo_dep, gstpbutils_dep ],
  install : true,
  install_dir : '@0@/gstreamer-1.0'.format(get_option('libdir')),
)
