dvdsub_sources = [
  'gstdvdsubdec.c',
  'gstdvdsubparse.c',
]

gstdvdsub = library('gstdvdsub',
  dvdsub_sources,
  c_args : ugly_args,
  include_directories : ugly_incs,
  dependencies : [gstbase_dep, gstvideo_dep],
  install : true,
  install_dir : '@0@/gstreamer-1.0'.format(get_option('libdir')),
)
