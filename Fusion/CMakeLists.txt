file(GLOB_RECURSE files "*.c")

add_library(Fusion ${files})

if(UNIX AND NOT APPLE)
    target_link_libraries(Fusion m) # link math library for Linux
endif()

install(TARGETS Fusion)

install(FILES Fusion.h FusionAhrs.h FusionAxes.h FusionCompass.h FusionCalibration.h FusionConvention.h FusionMath.h FusionOffset.h
        DESTINATION include/Fusion)
