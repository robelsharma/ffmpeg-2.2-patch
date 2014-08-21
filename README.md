ffmpeg-2.2-patch
================

ffmpeg-2.2 patch for relocation R_X86_64_PC32 against symbol error when compile in x64-bit


Scope of Issue: 
==========================================================================================================================================================================

When ffmpeg is built for static library and this compiled static library is linked with another dynamic library then the final linking failed with error --
```
ffmpeg/libavcodec/libavcodec.a(xx_yyyy.o): relocation R_X86_64_PC32 against symbol `ff_xx_yy_zz_qq' can not be used when making a shared object; recompile with -fPIC
/usr/bin/ld: final link failed: Bad value
collect2: ld returned 1 exit status
```
Machine:
--------

x64-bit
Linux, Unix, may be windows 64-bit


How to fix:
-----------

Use the ffmpeg-2.2.patch in your FFmpeg-n2.2 release source.


How to apply patch:
-------------------

1. Copy the downloaded patch to your FFmpeg-n2.2 folder.
2. Test the patch compatibility with your ffmpeg source by --

```
patch --dry-run -p1 -i  ffmpeg-2.2.patch
```

giving this command inside your ffmpeg source folder.

3. If the test returns no fail patch file then you are good to patch.

4. Now patch by following command --

patch -p1 -i ffmpeg-2.2.patch

5. Now enjoy linking with your any other project library !!



*Note: I am not in blame for any other issue and any other copyright law , if ffmpeg have any for this. This is only a remedy for the group who suffers from this compilation errors.*
