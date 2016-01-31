if dvdread_dep.found()
  dvdread = library('gstdvdread',
    'dvdreadsrc.c',
    c_args : ugly_args,
    include_directories : ugly_incs,
    dependencies : [ dvdread_dep, gstbase_dep ],
    install : true,
    install_dir : plugins_install_dir,
  )
endif
