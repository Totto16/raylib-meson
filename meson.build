project('raylib', 'c', version: '4.5.0', license: 'Zlib')

add_project_arguments(
    '-DPLATFORM_' + get_option('raylib_platform'),
    language: 'c',
)

deps = []
deps += dependency('glfw3')
deps += dependency('threads')
deps += dependency('dl')

# it also needs libm!
cc = meson.get_compiler('c')
deps += cc.find_library('m', required: true)

raylib_sources = [
    'raylib/src/raudio.c',
    'raylib/src/rcore.c',
    'raylib/src/rmodels.c',
    'raylib/src/rshapes.c',
    'raylib/src/rtext.c',
    'raylib/src/rtextures.c',
    'raylib/src/utils.c',
]

raylib_inc = include_directories('raylib/src')
# TODO: use library and allow consumers to pick the version they want
raylib_lib = static_library(
    'raylib',
    raylib_sources,
    dependencies: deps,
    include_directories: raylib_inc,
)

raylib_dep = declare_dependency(
    include_directories: raylib_inc,
    link_with: raylib_lib,
)
