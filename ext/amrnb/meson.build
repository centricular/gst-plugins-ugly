if amrnb_dep.found()
  amrnb = library('gstamrnb',
    [ 'amrnb.c', 'amrnbdec.c', 'amrnbenc.c' ],
    c_args : ugly_args,
    include_directories : ugly_incs,
    dependencies : [ amrnb_dep, gstaudio_dep ],
    install : true,
    install_dir : plugins_install_dir,
  )
endif
