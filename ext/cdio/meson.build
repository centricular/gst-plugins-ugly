if cdio_dep.found()
  cdio = library('gstcdio',
    [ 'gstcdio.c', 'gstcdiocddasrc.c' ],
    c_args : ugly_args,
    include_directories : ugly_incs,
    dependencies : [ cdio_dep, gstaudio_dep ],
    install : true,
    install_dir : plugins_install_dir,
  )
endif
