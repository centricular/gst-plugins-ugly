if twolame_dep.found()
  twolame = library('gsttwolame',
    'gsttwolamemp2enc.c',
    c_args : ugly_args,
    include_directories : ugly_incs,
    dependencies : [ twolame_dep, gstaudio_dep ],
    install : true,
    install_dir : plugins_install_dir,
  )
endif
