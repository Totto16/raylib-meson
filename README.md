# raylib-meson

[raylib](https://github.com/raysan5/raylib) build for [Meson](https://mesonbuild.com) projects.

## Usage

1. Create a [meson.build](examples/core_basic_window/meson.build) file

```meson
project('myproject', 'c')

raylib_dep = dependency('raylib', fallback: ['raylib', 'raylib_dep'])

executable('myproject', 'myproject.c',
  dependencies: [raylib_dep]
)
```
    
2. Create the subproject .wrap file:
    - [`subprojects/raylib.wrap`](examples/core_basic_window/subprojects/raylib.wrap)

3. Build the project

```bash
meson build
ninja -C build
```

See [the `examples` folder](examples) for one example.
