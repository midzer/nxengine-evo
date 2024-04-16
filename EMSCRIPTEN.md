# Emscripten

## Compile

```
mkdir build
cd build
emcmake cmake -DCMAKE_BUILD_TYPE=Release -DPORTABLE=ON ..
make
```

## Link

```
em++ -flto -O3 */*/*.o */*.o *.o -o index.html -sUSE_SDL=2 -sUSE_SDL_IMAGE=2 -sSDL2_IMAGE_FORMATS='["png"]' -sUSE_SDL_MIXER=2 -sUSE_LIBPNG -sASYNCIFY -sINITIAL_MEMORY=96mb --preload-file data/ --closure 1 -sEXPORTED_RUNTIME_METHODS=['allocate']
