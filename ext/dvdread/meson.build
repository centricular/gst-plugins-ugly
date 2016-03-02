dvdread_dep = dependency('dvdread', version : '>= 0.5.0', required : false)

if dvdread_dep.found()
  dvdread = library('gstdvdread',
    ['dvdreadsrc.c'],
    c_args : ugly_args,
    include_directories : ugly_incs,
    dependencies : [gstbase_dep, dvdread_dep],
    install : true,
    install_dir : plugins_install_dir,
  )
endif
