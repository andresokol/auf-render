set(GLSLC_EXECUTABLE_PATH "/home/andresokol/code/shaderc/build/glslc/glslc")
message(STATUS "Compiling shaders, GLSLC executable path set to \"${GLSLC_EXECUTABLE_PATH}\"")

set(SHADER_FILES
        "base.vert"
        "base.frag"
        )

foreach(SHADER_FILE IN LISTS SHADER_FILES)
    execute_process(COMMAND ${GLSLC_EXECUTABLE_PATH}
            "${PROJECT_SOURCE_DIR}/shaders/${SHADER_FILE}" "-o" "${PROJECT_BINARY_DIR}/shaders/${SHADER_FILE}.spv")
    message(STATUS "Compiled shader /shaders/${SHADER_FILE}")
endforeach()
