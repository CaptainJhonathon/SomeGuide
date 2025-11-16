# Cross-compile Arm64 in Fedora
## How to
There is a project -- [aarch64-linux-gnu-toolchain repo in fedora copr](https://copr.fedorainfracloud.org/coprs/lantw44/aarch64-linux-gnu-toolchain/)

You can enable the repo with the guide along the right side "Quick Enable" (make sure you use root or sudo)
```
dnf copr enable lantw44/aarch64-linux-gnu-toolchain 
```

Then follow the Installation Instructions
```
dnf install aarch64-linux-gnu-{binutils,gcc,glibc}
```

Now you can use aarch64-linux-gnu-gcc to compile the executable from c source to arm executable

However, the executable haven't test on the Tishan PI, the support for the PI is rare...

## The Story
The story begin with a day I bought a development-board "泰山派" (Taishan PI like Raspberry PI but made and desiged by china) like with 2g+16g using rk3566 chip(arm64). Although I want to learn more about Android system, I can't suffer any more while I have to face school exams...

So I must limit my orbit around desktop (Windows and Linux) OS etc.

Well, I admitted I haven't got all the time to research this small thing.

But things get better when I trying to use c++ libs (of course you can find those in other blogs) like SDL, SFML, FLTK.

Trying to work with these libs and make an own c++ project. This idea kept me to learn cmake and make, the abilitiy to work from source code to the executable.

At a time, I found the mingw provide a toolchain for those who need to compile for windows.

Somehow, I realized there must be something like this so that I can use source code and cross-compiler build the pack for the PI.

Then after searching I got the repo of fedora.