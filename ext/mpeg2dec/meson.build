if mpeg2_dep.found()
  mpeg2dec = library('gstmpeg2dec',
    'gstmpeg2dec.c',
    c_args : ugly_args,
    include_directories : ugly_incs,
    dependencies : [ mpeg2_dep, gstvideo_dep ],
    install : true,
    install_dir : '@0@/gstreamer-1.0'.format(get_option('libdir')),
  )
endif
