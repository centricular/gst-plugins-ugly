amrwb_dep = dependency('opencore-amrwb', version : '>= 0.1.3', required : false)

if amrwb_dep.found()
  amrwbdec = library('gstamrwbdec',
    ['amrwb.c', 'amrwbdec.c'],
    c_args : ugly_args,
    link_args : noseh_link_args,
    include_directories : [configinc],
    dependencies : [gstaudio_dep, amrwb_dep],
    install : true,
    install_dir : plugins_install_dir,
  )
endif
