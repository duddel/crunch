cmake_minimum_required(VERSION 3.6)
project(crunch)

# enforce C++11 and disable extensions
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# essential to prevent char*/wchar_t* conversion errors
ADD_DEFINITIONS(-DUNICODE)
ADD_DEFINITIONS(-D_UNICODE)

add_executable(${CMAKE_PROJECT_NAME}
  ${CMAKE_CURRENT_SOURCE_DIR}/crunch/binary.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/crunch/bitmap.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/crunch/GuillotineBinPack.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/crunch/hash.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/crunch/lodepng.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/crunch/MaxRectsBinPack.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/crunch/packer.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/crunch/Rect.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/crunch/str.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/crunch/main.cpp
)

target_include_directories(${CMAKE_PROJECT_NAME} PRIVATE
  ${CMAKE_CURRENT_SOURCE_DIR}/crunch/
)
