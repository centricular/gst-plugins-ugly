amrnb_dep = dependency('opencore-amrnb', version : '>= 0.1.3', required : false)

if amrnb_dep.found()
  amrnb = library('gstamrnb',
    ['amrnb.c', 'amrnbdec.c', 'amrnbenc.c'],
    c_args : ugly_args,
    link_args : noseh_link_args,
    include_directories : [configinc],
    dependencies : [gstaudio_dep, amrnb_dep],
    install : true,
    install_dir : plugins_install_dir,
  )
endif
