if a52_dep.found() and cc.has_function('a52_init', prefix : '#include <stdint.h>\n#include <a52dec/a52.h>')
  a52dec = library('gsta52dec',
    'gsta52dec.c',
    c_args : ugly_args,
    include_directories : ugly_incs,
    dependencies : [ a52_dep, orc_dep, gstaudio_dep ],
    install : true,
    install_dir : '@0@/gstreamer-1.0'.format(get_option('libdir')),
  )
endif
