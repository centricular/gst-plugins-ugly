if dvdread_dep.found()
  dvdread = library('gstdvdread',
    'dvdreadsrc.c',
    c_args : ugly_args,
    include_directories : ugly_incs,
    dependencies : [ dvdread_dep, gstbase_dep ],
    install : true,
    install_dir : '@0@/gstreamer-1.0'.format(get_option('libdir')),
  )
endif
