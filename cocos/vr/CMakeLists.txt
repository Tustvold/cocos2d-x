
if (IOS AND CMAKE_GENERATOR STREQUAL Xcode)
    set(CCVRGenericHeadTracker ${CMAKE_CURRENT_BINARY_DIR}/CCVRGenericHeadTracker.mm)
    ADD_CUSTOM_COMMAND(
        OUTPUT ${CCVRGenericHeadTracker}
        COMMAND cp ${CMAKE_CURRENT_SOURCE_DIR}/vr/CCVRGenericHeadTracker.cpp ${CCVRGenericHeadTracker}
        DEPENDS ${CMAKE_CURRENT_SOURCE_DIR}/vr/CCVRGenericHeadTracker.cpp
    )
else()
    set(CCVRGenericHeadTracker vr/CCVRGenericHeadTracker.cpp)
endif()

set(COCOS_VR_SRC
    vr/CCVRDistortion.cpp
    vr/CCVRDistortionMesh.cpp
    vr/CCVRGenericRenderer.cpp
    ${CCVRGenericHeadTracker}
)
