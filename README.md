Nginx for Android
====================

Nginx Base Version
====================

Nginx release 1.7.0

Build Manual
====================

Install build tools
--------------------
Install following build tools.

* Android SDK - http://developer.android.com/sdk/index.html
* Android NDK - http://developer.android.com/tools/sdk/ndk/index.html

| name | value |
| :--- | :---- |
| HOME | Your home directory |
| ANDROID_HOME | Android SDK install path |
| ANDROID_NDK_HOME | Android NDK install path |

And, make standalone toolchain.

```
#!sh
% $ANDROID_NDK_HOME/build/tools/make-standalone-toolchain.sh \
    --platform=android-19 --install-dir=$HOME/local/android-toolchain
```


Configuration nginx core and modules
--------------------
Connect android device with USB cable, or launch android emulator.

Run command to configure nginx core and libraries.

```
#!sh
% auto/configure \
    --crossbuild=android-arm \
    --prefix=/sdcard/nginx \
    --with-cc=$HOME/local/android-toolchain/arm-linux-androideabi/bin/gcc \
    --without-pcre --without-http_rewrite_module --without-http_userid_module \
    --with-cc-opt=-Wno-sign-compare
```

License
====================

The application released under [WTFPL]

                DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE
                        Version 2, December 2004

     Copyright (C) 2014 Naoki Takimura <n.takimura@gmail.com>

     Everyone is permitted to copy and distribute verbatim or modified
     copies of this license document, and changing it is allowed as long
     as the name is changed.

                DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE
       TERMS AND CONDITIONS FOR COPYING, DISTRIBUTION AND MODIFICATION

      0. You just DO WHAT THE FUCK YOU WANT TO.

Nginx's license is not [WTFPL].
Check its license in http://nginx.org/LICENSE .


[developers.android.com]: http://developer.android.com/tools/sdk/ndk/index.html
[nginx]: http://nginx.com/
[WTFPL]: http://www.wtfpl.net/
[nginx-license]: http://nginx.org/LICENSE
