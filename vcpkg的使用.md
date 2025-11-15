# vcpkg的使用



## 启动vcpkg
1. 方法1

   ```cmake
   # 在cmake头部设置
   set(CMAKE_TOOLCHAIN_FILE "C:/Users/medusa/.vcpkg-clion/vcpkg/scripts/buildsystems/vcpkg.cmake")
   
   ```
2. clion 链接到当前项目
3. 安装
```bash
vcpkg install ffmpeg[all]
```

## ffmpeg
```cmake
find_package(FFMPEG REQUIRED)
  target_include_directories(main PRIVATE ${FFMPEG_INCLUDE_DIRS})
  target_link_directories(main PRIVATE ${FFMPEG_LIBRARY_DIRS})
  target_link_libraries(main PRIVATE ${FFMPEG_LIBRARIES})

ffmpeg provides pkg-config modules:

  # FFmpeg codec library
  libavcodec

  # FFmpeg device handling library
  libavdevice

  # FFmpeg audio/video filtering library
  libavfilter

  # FFmpeg container format library
  libavformat

  # FFmpeg utility library
  libavutil

  # FFmpeg audio resampling library
  libswresample

  # FFmpeg image rescaling library
  libswscale
```

## sdl2
```cmake
        find_package(SDL2 CONFIG REQUIRED)
       target_link_libraries(main
           PRIVATE
           $<TARGET_NAME_IF_EXISTS:SDL2::SDL2main>
           $<IF:$<TARGET_EXISTS:SDL2::SDL2>,SDL2::SDL2,SDL2::SDL2-static>
       )
```
## imgui-sfml 

```cmake

```


echo "# docment" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:airverger/docment.git
git push -u origin main
