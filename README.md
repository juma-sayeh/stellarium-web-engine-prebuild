Stellarium Web Engine
=====================

About
-----

Stellarium Web Engine is a JavaScript planetarium renderer using
WebGL that can be embedded into a website.

Features
--------

- Atmosphere simulation.
- Gaia stars database access (more than 1 billion stars).
- HiPS surveys rendering.
- High resolution planet textures.
- Constellations.
- Support for adding layers and shapes in the sky view.
- Landscapes.


Build the javascript version
----------------------------

You need to make sure you have both emscripten 1.40.1 and sconstruct installed.

    # 1.to install emscripten:
    
    git clone https://github.com/emscripten-core/emsdk.git
    cd emsdk
    
    # 2. if you're using arm machine (apple silicon) open terminal in rosetta (close it -> right click info -> check open with rosetta) and modify the emsdk.py file for x84_64 arch

    nano emsdk.py
    # then find   ARCH = 'arm64' or ARCH = 'arm' and change it to ARCH = 'x86_64'

    # install 1.40.1 emsdk (newer versions will not build)
    ./emsdk install 1.40.1
    ./emsdk activate 1.40.1
    source ./emsdk_env.sh


    # to install sconstruct
    export PATH="$PATH_TO_EMSDK/python/3.13.3_64bit/bin:$PATH"
    # Validate that python is indeed 3.13:
    python3 -V
    
    # install scons for the current session python wich is the same one for emsdk
    pip3 install scons

    # Build stellarium-web-engine.js and stellarium-web-engine.wasm
    # This will also copy the files into html/static/js
    make js

    # Now see apps/simple-html/ to try the library in a browser.


Contributing
------------

In order for your contribution to Stellarium Web Engine to be accepted, you have to sign the
[Stellarium Web Contributor License Agreement (CLA)](doc/cla/sign-cla.md).
