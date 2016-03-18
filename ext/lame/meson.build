lame_dep = cc.find_library('mp3lame', required : false)

if lame_dep.found() and cc.has_function('lame_init', prefix : '#include <lame/lame.h>')
  lame_extra_c_args = []
  if cc.has_function('lame_set_VBR_quality', prefix : '#include <lame/lame.h>')
    lame_extra_c_args += ['-DHAVE_LAME_SET_VBR_QUALITY']
  endif
  if cc.compiles('#include <lame/lame.h>\nint preset = MEDIUM;')
    lame_extra_c_args += ['-DGSTLAME_PRESET']
  endif
  lame = library('gstlame',
    ['gstlamemp3enc.c', 'plugin.c'],
    c_args : ugly_args + lame_extra_c_args,
    include_directories : ugly_incs,
    dependencies : [gstaudio_dep, lame_dep],
    install : true,
    install_dir : plugins_install_dir,
  )
endif
