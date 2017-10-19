Compile Exploits
================


i686-w64-mingw32-gcc 21071.c -o bob.exe  -lkernel32 -luser32 -lgdi32 -lcomdlg32 -lole32 -ldinput -lddraw -ldxguid -lwinmm -ldsound -lws2_32