FFmpeg README
=============

FFmpeg is a collection of libraries and tools to process multimedia content
such as audio, video, subtitles and related metadata.

## Libraries

* `libavcodec` provides implementation of a wider range of codecs.
* `libavformat` implements streaming protocols, container formats and basic I/O access.
* `libavutil` includes hashers, decompressors and miscellaneous utility functions.
* `libavfilter` provides a mean to alter decoded Audio and Video through chain of filters.
* `libavdevice` provides an abstraction to access capture and playback devices.
* `libswresample` implements audio mixing and resampling routines.
* `libswscale` implements color conversion and scaling routines.

## Tools

* [ffmpeg](https://ffmpeg.org/ffmpeg.html) is a command line toolbox to
  manipulate, convert and stream multimedia content.
* [ffplay](https://ffmpeg.org/ffplay.html) is a minimalistic multimedia player.
* [ffprobe](https://ffmpeg.org/ffprobe.html) is a simple analysis tool to inspect
  multimedia content.
* Additional small tools such as `aviocat`, `ismindex` and `qt-faststart`.

## Documentation

The offline documentation is available in the **doc/** directory.

The online documentation is available in the main [website](https://ffmpeg.org)
and in the [wiki](https://trac.ffmpeg.org).

### Examples

Coding examples are available in the **doc/examples** directory.

## License

FFmpeg codebase is mainly LGPL-licensed with optional components licensed under
GPL. Please refer to the LICENSE file for detailed information.

## Contributing

Patches should be submitted to the ffmpeg-devel mailing list using
`git format-patch` or `git send-email`. Github pull requests should be
avoided because they are not part of our review process and will be ignored.
# FFMPEG_ANDROID
开源ffmpeg集成到android

# Config脚本----20191116
android_build.sh及build_one.sh都能编译通过
20191130
1、使用android_build.sh编译.a文件，把.a文件放到其他jni模块打包成一个so，编译报错（报错的是jni.h定义的变量找不到，很奇怪。不集成这些.a文件是能正常编译出jni的）
2、如果把编译好的.a文件打包编译成一个单独so，再把so放到jni模块去编译，还是报步骤1的错

3、androi_one.sh编译出来8个so文件，把这几个so文件及include目录拷贝到jni模块，编译没问题
4、jni编译出来的8个so及jni生成的so放到android工程里运行也没问题

20191203
1、使用build_one.sh及buiold_one_a.sh编译出来的so都可用
2、测试demo：https://github.com/zhan3080/FFmpegPlayer.git 
