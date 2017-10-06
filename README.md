# Opencv 3.2 + cuda 9.0 + tesseract 를 vs2017에서 빌드하는 방법을 설명

cuda 9.0이 vs2017에서 빌드할 수 있다고 해서 opencv의 cuda를 시험 해볼겸 빌드를 시작했다.
cuda 9.0과 opencv 3.2가 호환되지 않는 것인지 추가 작업을 해야 빌드할 수 있었다. 

vs2017은 BOM이 없는 UTF8 소스파일에서 Warning이 발생하면 메시지 글자가 깨져서 읽을 수 없었다. warning 메시지를 읽으려면
utf8 BOM이나 유니코드로 인코딩을 바꿔야 했다. bom이 없는 utf8파일인데 유니코드 모든 글자가 들어있는 파일은 컴파일 에러가 발생하기도 했다. 

## 빌드환경

### 윈도우 10 홈
### vs2017 community
### cmake 최신
### cppan client 최신
### nvidia 그래픽 카드 (맥스웰 이상) : GTX1080
### opencv 3.2.0
### opencv_contrib 3.2.0
### tesseract 3.05.1
### cuda toolkit 9.0.176

## 빌드절차

### tesseract 빌드
CPPAN을 소스 폴더에서 실행하여 빌드에 필요한 라이브러리를 다운 받는다.
CMAKE를  VS2017 X64용 솔루션파일을 만들고
VS2017에서 빌드한다. 에러가 있는 파일의 인코딩을 utf8-bom으로 바꿔주고 다시 빌드한다.

### opencv 빌드

## 참고

(구글번역) http://tinyland.site/posts/2017-06-19-Win10-VS2017-compile-opencv3-2-0-and-opencv-contrib3-2-0-to-call-the-text-module.html

https://github.com/tesseract-ocr/tesseract/wiki/Compiling#windows

https://stackoverflow.com/questions/45525377/installing-opencv-3-3-0-with-contrib-modules-using-cmake-cuda-9-0-rc-and-visual

http://docs.nvidia.com/cuda/cuda-compiler-driver-nvcc/index.html#gpu-feature-list

https://devtalk.nvidia.com/default/topic/1021038/compile-cuda-win7x64-vs2017-nvcc-fatal-host-compiler-targets-unsupported-os-/

 

