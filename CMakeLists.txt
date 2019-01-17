# For more information about using CMake with Android Studio, read the
# documentation: https://d.android.com/studio/projects/add-native-code.html

# Sets the minimum version of CMake required to build the native library.

cmake_minimum_required(VERSION 3.4.1)

include_directories(
        ${CMAKE_CURRENT_SOURCE_DIR}
        ${CMAKE_CURRENT_SOURCE_DIR}/include)

set(soundtouch_files
        source/SoundTouch/AAFilter.cpp
        source/SoundTouch/FIFOSampleBuffer.cpp
        source/SoundTouch/FIRFilter.cpp
        source/SoundTouch/cpu_detect_x86.cpp
        source/SoundTouch/sse_optimized.cpp
        source/SoundTouch/RateTransposer.cpp
        source/SoundTouch/InterpolateCubic.cpp
        source/SoundTouch/InterpolateLinear.cpp
        source/SoundTouch/InterpolateShannon.cpp
        source/SoundTouch/TDStretch.cpp
        source/SoundTouch/BPMDetect.cpp
        source/SoundTouch/PeakFinder.cpp
        source/SoundTouch/SoundTouch.cpp
        source/SoundTouch/mmx_optimized.cpp
        ijksoundtouch_wrap.cpp
        )

add_library(ijksoundtouch
        STATIC
        ${soundtouch_files})
