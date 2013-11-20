set(COCOS2D_SRC
  CCAction.cpp
  CCActionCamera.cpp
  CCActionEase.cpp
  CCActionGrid.cpp
  CCActionGrid3D.cpp
  CCActionInstant.cpp
  CCActionInterval.cpp
  CCActionManager.cpp
  CCActionPageTurn3D.cpp
  CCActionProgressTimer.cpp
  CCActionTiledGrid.cpp
  CCActionCatmullRom.cpp
  CCActionTween.cpp
  CCAtlasNode.cpp
  CCNode.cpp
  CCEventAcceleration.cpp
  CCEventListenerAcceleration.cpp
  CCEvent.cpp
  CCEventDispatcher.cpp
  CCEventListener.cpp
  CCEventKeyboard.cpp
  CCEventListenerKeyboard.cpp
  CCEventMouse.cpp
  CCEventListenerMouse.cpp
  CCTouch.cpp
  CCEventTouch.cpp
  CCEventListenerTouch.cpp
  CCEventCustom.cpp
  CCEventListenerCustom.cpp
  CCDrawingPrimitives.cpp
  CCDrawNode.cpp
  CCGrabber.cpp
  CCGrid.cpp
  CCFont.cpp
  CCFontAtlas.cpp
  CCFontAtlasCache.cpp
  CCFontAtlasFactory.cpp
  CCFontDefinition.cpp
  CCFontFNT.cpp
  CCFontFreeType.cpp
  CCLabel.cpp
  CCLabelAtlas.cpp
  CCLabelBMFont.cpp
  CCLabelTTF.cpp
  CCLabelTextFormatter.cpp
  CCTextImage.cpp
  CCLayer.cpp
  CCScene.cpp
  CCTransition.cpp
  CCTransitionPageTurn.cpp
  CCTransitionProgress.cpp
  CCMenu.cpp
  CCMenuItem.cpp
  CCMotionStreak.cpp
  CCProgressTimer.cpp
  CCClippingNode.cpp
  CCRenderTexture.cpp
  CCParticleExamples.cpp
  CCParticleSystem.cpp
  CCParticleSystemQuad.cpp
  CCParticleBatchNode.cpp
  CCScriptSupport.cpp
  CCAnimation.cpp
  CCAnimationCache.cpp
  CCSprite.cpp
  CCSpriteBatchNode.cpp
  CCSpriteFrame.cpp
  CCSpriteFrameCache.cpp
  ccUTF8.cpp
  CCProfiling.cpp
  CCUserDefault.cpp
  TransformUtils.cpp
  base64.cpp
  ccUtils.cpp
  CCVertex.cpp
  CCNotificationCenter.cpp
  TGAlib.cpp
  ZipUtils.cpp
  ccCArray.cpp
  CCComponent.cpp
  CCComponentContainer.cpp
  CCIMEDispatcher.cpp
  CCTextFieldTTF.cpp
  CCTexture2D.cpp
  CCTextureAtlas.cpp
  CCTextureCache.cpp
  CCParallaxNode.cpp
  CCTMXLayer.cpp
  CCTMXObjectGroup.cpp
  CCTMXTiledMap.cpp
  CCTMXXMLParser.cpp
  CCTileMapAtlas.cpp
  CCGLProgram.cpp
  ccGLStateCache.cpp
  CCShaderCache.cpp
  ccShaders.cpp
  CCCamera.cpp
  CCConfiguration.cpp
  CCDirector.cpp
  CCScheduler.cpp
  ccFPSImages.c
  ccTypes.cpp
  cocos2d.cpp
  CCDeprecated.cpp
  platform/CCSAXParser.cpp
  platform/CCThread.cpp
  platform/CCEGLViewProtocol.cpp
  platform/CCFileUtils.cpp
  platform/mac/CCApplication.mm
  platform/mac/CCCommon.mm
  platform/mac/CCDevice.mm
  platform/mac/CCDirectorCaller.mm
  platform/mac/CCEGLView.mm
  platform/mac/CCEventDispatcherMac.mm
  platform/mac/CCImage.mm
  platform/mac/CCWindow.mm
  platform/mac/EAGLView.mm
  platform/apple/CCLock.cpp
  platform/apple/CCFileUtilsApple.mm
  platform/apple/CCThread.mm
)
  

include(../physics/CMakeLists.txt)

add_library(cocos2d STATIC
  ${COCOS2D_SRC}
  ${COCOS_PHYSICS_SRC}
)

target_link_libraries(cocos2d
  cocosbase
  chipmunk_static
  tinyxml2
  kazmath
  unzip
  jpeg
  tiff
  freetype
  png
  pthread
  z
  glfw3
  sqlite3
  curl
  webp
  network
  "-framework Foundation"
  "-framework AudioUnit"
  "-framework AudioToolbox"
  "-framework ApplicationServices"
  "-framework OpenAL"
  "-framework Carbon"
  "-framework Cocoa"
  "-framework CoreAudio"
  "-framework ForceFeedback"
  "-framework IOKit"
  "-framework OpenGL"
  "-framework CoreServices"
  "-framework QuartzCore"
  "-framework IOKit"
)

set_target_properties(cocos2d
    PROPERTIES
    ARCHIVE_OUTPUT_DIRECTORY "${CMAKE_SOURCE_DIR}/lib"
    LIBRARY_OUTPUT_DIRECTORY "${CMAKE_SOURCE_DIR}/lib"
)

