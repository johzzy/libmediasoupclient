## 参考
https://mediasoup.org/documentation/v3/libmediasoupclient/installation/


## webrtc
```bash
cd {/path/to/webrtc/src}
gclient sync

#? m??

gn gen out/libmediasoupclient --args='is_debug=false is_component_build=false is_clang=true rtc_include_tests=false rtc_use_h264=true use_rtti=true use_custom_libcxx=false'
ninja -C out/libmediasoupclient
```

## mediasoup
```bash
cd {/path/to/libmediasoupclient}
cmake . -Bbuild \
  -DLIBWEBRTC_INCLUDE_PATH:PATH={/path/to/webrtc/src} \
  -DLIBWEBRTC_BINARY_PATH:PATH={/path/to/webrtc/src}/out/libmediasoupclient/obj
make -C build/
#clion -DLIBWEBRTC_INCLUDE_PATH:PATH=${WEBRTC_PATH} -DLIBWEBRTC_BINARY_PATH:PATH=${WEBRTC_PATH}/out/libmediasoupclient/obj
```

## 学习
https://blog.csdn.net/A18373279153/article/details/111415518