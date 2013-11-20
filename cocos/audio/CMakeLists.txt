set(AUDIO_M_SRC
    mac/CDAudioManager.m
    mac/CDOpenALSupport.m
    mac/CocosDenshion.m
    mac/SimpleAudioEngine_objc.m
)

set(AUDIO_MM_SRC
    mac/CDXMacOSXSupport.mm
    mac/SimpleAudioEngine.mm
)


set(CMAKE_CXX_FLAGS "")

SET_SOURCE_FILES_PROPERTIES(${AUDIO_MM_SRC}
  PROPERTIES
  COMPILE_FLAGS "${CMAKE_CXX_FLAGS} -x objective-c++ -std=c++11 -stdlib=libc++")


add_library(audio STATIC
  ${AUDIO_M_SRC}
  ${AUDIO_MM_SRC}
)

set_target_properties(audio
    PROPERTIES
    ARCHIVE_OUTPUT_DIRECTORY "${CMAKE_SOURCE_DIR}/lib"
    LIBRARY_OUTPUT_DIRECTORY "${CMAKE_SOURCE_DIR}/lib"
)

