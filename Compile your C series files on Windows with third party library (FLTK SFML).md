# Compile your C series files on Windows with third party library

***This document mainly solve the problem that you want to use a third party library to build your own program but failed at compiling***

By the way, two libraries FLTK, SFML had been confirmed by myself,
using cmake and MSCV(installed from Visual Studio) is easy to compile.

Strongly recommend to use cmake-gui for beginners.

Msys2 still need to fix up Windows SDK, So that's why I fix my solution. 

## (Optional) the principle of compiling

There are four main stages to generate an executable program from a source code file.

1. Preprocessing
2. Compilation
3. Assembly
4. Linking

More info just check the Internet

## Compiling with third party library by Msys2 (using FLTK, SFML for example)

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

## Compiling with third party library by cmake and Visual Studio (using FLTK, SFML for example)

The cmake can easy to build the library.

I'll tell seperately.

## 1. SFML
SFML provide builded package. However, official document tutorial give a better guide. The guide is right, but you'll still need to install SDK in Visual Studio(which never told clearly in these doucments).

## 2. FLTK
FLTK provide a source package. You need to build the library by cmake-gui (the easy way).

**1.1 building fltk**

After configure and build by cmake, you will find a file like FLTK.sln, solution file of Visual Studio.

Through opening, There a bunch of solutions. 

Find the ALL_BUILD solution, 

make sure your running option is "Debug" or "Release" (both need to build), 

right click the solution and click "build",

changing option then use right click "rebuild".

**1.2 move files to right folders**

Now I assume you're in "build" folder under fltk, you need to move "fl_config.h" that under "FL" to the same name folder under root of fltk. This is nessary beacause fltk need this header to work.

.libs files are in build/lib/Debug(Release). If you want to make path easier you can do the same like "fl_config.h" but to "lib" folder.

**1.3 cofigure Visual Studio**

Starting a new blank project, adding a .cpp file.

From top column "project" find project property.

Finding "C/C++" , in "General", paste your fltk path to "Additional Include Directories".

Finding "Linker", in "General", paste your fltk libs path to "Additional Library Directories". In "Input", refer to official documents, adding lib to "Additional Dependencies", fltk.lib etc.

# However you need to know

## Update in 2025/11
I'm not recommend using VS to continue your project (unless you get a reason). Using cmake to organise the c/c++ project will get cross-platform and more light-weight for your development space.

## How can I know what library should I specify?
All the libraries that compile needs can be found at the official documents.

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
