a52_dep = cc.find_library('a52', required : false)

if a52_dep.found() and cc.has_function('a52_init', prefix : '#include <stdint.h>\n#include <a52dec/a52.h>')
  a52dec = library('gsta52dec',
    'gsta52dec.c',
    c_args : ugly_args,
    include_directories : ugly_incs,
    dependencies : [gstaudio_dep, orc_dep, a52_dep],
    install : true,
    install_dir : plugins_install_dir,
  )
endif
