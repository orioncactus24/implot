cmake_minimum_required(VERSION 3.28)

project(implot)

file(GLOB  SOURCE_FILES "${CMAKE_CURRENT_LIST_DIR}/*.cpp")

add_library(${PROJECT_NAME} STATIC ${SOURCE_FILES})
add_library(dependencies::implot ALIAS ${PROJECT_NAME})

target_include_directories(${PROJECT_NAME} PUBLIC
${CMAKE_CURRENT_LIST_DIR}
)

target_link_libraries(${PROJECT_NAME} PUBLIC dependencies::imgui)

# # Set where the ImGui files are stored
# set(IMGUI_PATH  "abstract/folder/where/is/stored")
    
# # Compile as static library 
# file(GLOB IMGUI_SOURCES ${IMGUI_PATH}/*.cpp) 
# add_library("ImGui" STATIC ${IMGUI_SOURCES})
# target_include_directories("ImGui" PUBLIC ${IMGUI_PATH})