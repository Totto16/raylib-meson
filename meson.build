project('raylib', 'c',
  version : '2.0.1-alpha',
  license: 'Zlib'
)

add_project_arguments('-DPLATFORM_' + get_option('raylib_platform'),
  language: 'c'
)

glfw_dep = dependency('glfw3')

raylib_sources = [
  'raylib/src/audio.c',
  'raylib/src/core.c',
  'raylib/src/models.c',
  'raylib/src/shapes.c',
  'raylib/src/text.c',
  'raylib/src/textures.c',
  'raylib/src/utils.c',
  'raylib/src/external/mini_al.c',
]

raylib_inc = include_directories('raylib/src')
# TODO: use library and allow consumers to pick the version they want
raylib_lib = static_library('raylib',
  raylib_sources,
  dependencies: glfw_dep,
  include_directories: raylib_inc
)

raylib_dep = declare_dependency(
  include_directories: raylib_inc,
  link_with: raylib_lib
)
