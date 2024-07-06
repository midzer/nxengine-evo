# Emscripten

## Compile

```
mkdir build
cd build
emcmake cmake -DCMAKE_BUILD_TYPE=Release -DPORTABLE=ON ..
emmake make
```

## Link

```
em++ -flto -O3 */*/*.o */*.o *.o -o index.html -sUSE_SDL=2 -sUSE_SDL_IMAGE=2 -sSDL2_IMAGE_FORMATS='["png","bmp"]' -sUSE_SDL_MIXER=2 -sASYNCIFY -sASYNCIFY_IGNORE_INDIRECT -sASYNCIFY_ONLY=@../../../../funcs.txt -sINITIAL_MEMORY=128mb -sENVIRONMENT=web --preload-file ../../../../data/@data/ --closure 1 -sEXPORTED_RUNTIME_METHODS=['allocate']
```
