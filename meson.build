project('vivtc', 'c', 'cpp',
  version : '1',
  default_options : ['warning_level=3', 'buildtype=release', 'b_ndebug=if-release'])

add_project_arguments('-ffast-math', language : 'c')

sources = [
     'src/vivtc.c'
]

vapoursynth_dep = dependency('vapoursynth', version: '>=55').partial_dependency(compile_args : true, includes : true)

deps = [vapoursynth_dep]

shared_module('vivtc', sources,
  dependencies : deps,
  install : true,
  install_dir : join_paths(vapoursynth_dep.get_pkgconfig_variable('libdir'), 'vapoursynth'),
  gnu_symbol_visibility : 'hidden'
)
