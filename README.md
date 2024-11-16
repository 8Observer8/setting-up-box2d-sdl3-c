Setting up SDL3 3.1.6 and Box2D 3.0.0 with CMake and the C language for Desktop and WebAssembly.

The [preview-3.1.6/examples/renderer/01-clear/clear.c](https://github.com/libsdl-org/SDL/blob/preview-3.1.6/examples/renderer/01-clear/clear.c) example is used.

Migration guide: https://github.com/erincatto/box2d/blob/main/docs/migration.md

The -DSDL3_DIR must be changed in the `config-win.bat` and `config-web.bat` to your installation path. Install: CMake, MinGW, SDL3, and [emsdk](https://emscripten.org/docs/getting_started/downloads.html).

The installation Box2D paths in `target_include_directories` and `target_link_directories` in `CMakeLists.txt` must be changed to yours.

Building to EXE in CMD:
- config-win
- build-win

Building to WASM in CMD:
- config-web
- build-web
- the `app.js` and `app.wasm` files will be generated in the `public` folder
