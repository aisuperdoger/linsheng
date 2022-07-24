项目的目录结构为：
```
├── bin
│   └── 07-03-extract-h264
├── ffmpeg-4.2.7
│   ├── include
│   └── lib
├── sources
│   ├── believe.flv
│   └── believe.mp4
├── src
|   ├── 07-01-demux.c
|   ├── 07-02-extract-aac.c
|   └── 07-03-extract-h264.c
├── README.md
```

其中ffmpeg-4.2.7中包含ffmpeg的库文件和头文件

sources包含代码所用的音视频知识的pdf资料，可以从[这里](https://www.aliyundrive.com/s/wsZH1U7x3kh)获取到。

与各个代码相关的学习资料,可以从[这里](https://www.aliyundrive.com/s/wsZH1U7x3kh)获取到。




运行代码：
```
src/07-01-demux.c:
gcc src/07-01-demux.c -o bin/07-01-demux  -g  -L ffmpeg-4.2.7/lib  -l avformat -l avcodec -l avutil -lm -I ffmpeg-4.2.7/include -Wl,-rpath=ffmpeg-4.2.7/lib # 编译
bin/07-01-demux   # 运行

src/07-02-extract-aac.c:
gcc src/07-02-extract-aac.c -o bin/07-02-extract-aac  -g  -L ffmpeg-4.2.7/lib  -l avformat -l avcodec -l avutil -lm -I ffmpeg-4.2.7/include -Wl,-rpath=ffmpeg-4.2.7/lib # 编译
bin/07-02-extract-aac sources/believe.mp4  sources/believe_out.aac  # 运行

src/07-03-extract-h264.c:
gcc src/07-03-extract-h264.c -o bin/07-03-extract-h264  -g  -L ffmpeg-4.2.7/lib  -l avformat -l avcodec -l avutil -lm -I ffmpeg-4.2.7/include -Wl,-rpath=ffmpeg-4.2.7/lib # 编译
bin/07-03-extract-h264    sources/believe.mp4  sources/believe_out.h264  # 运行


07-04-flv-parse:
g++ main.cpp FlvMetaData.cpp FlvParser.cpp vadbg.cpp Videojj.cpp -o main




```



ffmpeg版本：4.2.7