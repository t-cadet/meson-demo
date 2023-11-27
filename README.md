# Meson Demo

```bash
meson compile -C build # build project
./build/main # run project
meson test -C build # run tests
ninja -C build clang-format # format code
meson setup build-ubsan -Db_sanitize=undefined # setup a build with UB sanitizer
```
