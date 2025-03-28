# gnuplot.js

Port of GnuPlot to JavaScript using Emscripten.

GnuPlot is a command-line program that can generate two- and three-dimensional plots of functions, data, and data fits. The program runs on all major computers and operating systems.


## Getting Started 

Emscripten is a toolchain for compiling to asm.js and WebAssembly, built using LLVM, that lets you run C and C++ on the web at near-native speed without plugins.

More Info : https://emscripten.org/

Installation guide: https://emscripten.org/docs/getting_started/downloads.html


### Installing

For Creating gnuplot.js
After installing emscripten, add emcc to environment variable

```
cd emsdk
source ./emsdk_env.sh
```

Clone this repo

To generate gnuplot.o
```
cd gnuplot.js
cd src
emconfigure ./configure
emmake make
emmake make install
cp ./src/gnuplot ../gnuplot.o
cd ..
```

Generate gnuplot.js

```
emcc -s WASM=0 -O2 -s FORCE_FILESYSTEM=1 -s 'EXTRA_EXPORTED_RUNTIME_METHODS=["intArrayFromString","intArraytoString"]' gnuplot.o -o gnuplot.js --pre-js pre.js
```

## Contributors

<a href="https://github.com/YasasviPeruvemba/"><b>Yasasvi Peruvemba</b></a><br>
<a href="https://github.com/ajit3259/"><b>Ajit Kumar</b></a>

## Source Files
The source files for GnuPlot without any modification can be found at the repository of <a href="https://github.com/ajit3259/"><b>Ajit Kumar</b></a>

## Authors

  Copyright 1986 - 1993, 1998, 2004   Thomas Williams, Colin Kelley
 
  Permission to use, copy, and distribute this software and its
  documentation for any purpose with or without fee is hereby granted,
  provided that the above copyright notice appear in all copies and
  that both that copyright notice and this permission notice appear
  in supporting documentation.
 
  Permission to modify the software is granted, but not the right to
  distribute the complete modified source code.  Modifications are to
  be distributed as patches to the released version.  Permission to
  distribute binaries produced by compiling modified sources is granted,
  provided you
  
    1. Distribute the corresponding source modifications from the
     released version in the form of a patch file along with the binaries,
    2. Add special version identification to distinguish your version
     in addition to the base release version number,
    3. Provide your name and address as the primary contact for the
     support of your modified version, and
    4. Retain our contact information in regard to use of the base
     software.
     
  Permission to distribute the released version of the source code along
  with corresponding source modifications in the form of a patch file is
  granted with same provisions 2 through 4 for binary distributions.
 
  This software is provided "AS IS" without express or implied warranty
  to the extent permitted by applicable law.

