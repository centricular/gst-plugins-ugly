cdio_dep = dependency('libcdio', version : '>= 0.76', required : false)

if cdio_dep.found()
  cdio = library('gstcdio',
    ['gstcdio.c', 'gstcdiocddasrc.c'],
    c_args : ugly_args,
    include_directories : ugly_incs,
    dependencies : [gstaudio_dep, cdio_dep],
    install : true,
    install_dir : plugins_install_dir,
  )
endif
