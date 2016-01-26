if mad_dep.found()
  mad = library('gstmad',
    'gstmad.c',
    c_args : ugly_args,
    include_directories : ugly_incs,
    dependencies : [ mad_dep, gstaudio_dep ],
    install : true,
    install_dir : '@0@/gstreamer-1.0'.format(get_option('libdir')),
  )
endif
