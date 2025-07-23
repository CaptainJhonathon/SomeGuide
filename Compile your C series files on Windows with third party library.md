# Compile your C series files on Windows with third party library

***This document mainly solve the problem that you want to use a third party library to build your own program but failed at compiling***

By the way, two libraries FLTK, SFML had been confirmed by myself,

IF YOU WANT TO USE THOSE C++ THIRD PARTY LIBRARY ***ESPACIALLY DOING IN VISUAL STUDIO ALONE*** YOU WILL STUCK FOR A LONG TIME!!! AND I DON'T GET A SINGLE SUCCESS BY USING WINDOWS DEVELOP ENVIORNMENT.

The only way I success is using Msys2 on Windows

PS: though this I thing no one would like to stuck in such a environment just for figuring out how to use a library. Now I see a little why saying C++ is difficult.

## (Optional) the principle of compiling

There are four main stages to generate an executable program from a source code file.

1. Preprocessing
2. Compilation
3. Assembly
4. Linking

More info just check the Internet

## Compiling with third party library (using FLTK, SFML for example)

***Assuming you had setup Msys2***

Universally, using compiler (gcc g++) will provide option to locate your using head files and libraries.

simple example:
```
g++ hello.cxx -o hello.exe -I /headers/include -L /library/include -l specific_library
```

Explaing:

1. -I : locate headers file directory
2. -L : locate libraries file directory
3. -l : tell the linker what library need to use (***IMPORTANT !!!***)
----
### Reality Example:

**Using Msys2 UCRT64**

PS: Msys2 will help you with the directory unless you install them customly. **So you don't need to specify the two directories every time**.

#### 1. FLTK
----
Get the hello.cxx from official document.
```
g++ hello.cxx -o hello.exe -I /ucrt64/include -L /ucrt64/lib -l fltk
```

By my saying "PS" you can also using in Msys2 (this work same for SFML):
```
g++ hello.cxx -lfltk
```


#### 2. SFML
----
Get the main.cpp from official document.
```
g++ main.cpp -o main.exe -I /ucrt64/include -L /ucrt64/lib -lsfml-graphics -lsfml-window -lsfml-system
```

# However you need to know

## How can I know what library should I specify?
Well, if you checking the official document, there should be some tips (whether they make it clear...). Usually in Chapter Building/Linking or README, Makefile.example

## Useful tools to locate library

1. fltk-config  
    provided by fltk itself.
---

2. pkg-config   
    by reading .pc files
```
pkg-config --libs sfml-all
```

----
# May this help you. WANT TO LEARN MORE? GO TO OFFICIAL DOCUMENTS
