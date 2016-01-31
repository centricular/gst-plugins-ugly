if mad_dep.found()
  mad = library('gstmad',
    'gstmad.c',
    c_args : ugly_args,
    include_directories : ugly_incs,
    dependencies : [ mad_dep, gstaudio_dep ],
    install : true,
    install_dir : plugins_install_dir,
  )
endif
