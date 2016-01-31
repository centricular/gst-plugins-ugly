if amrwb_dep.found()
  amrwbdec = library('gstamrwbdec',
    [ 'amrwb.c', 'amrwbdec.c' ],
    c_args : ugly_args,
    include_directories : ugly_incs,
    dependencies : [ amrwb_dep, gstaudio_dep ],
    install : true,
    install_dir : plugins_install_dir,
  )
endif
