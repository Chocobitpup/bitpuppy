cmake_minimum_required(VERSION 3.16)
project(bitpuppy)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Find dependencies
find_package(yaml-cpp REQUIRED)
find_package(nlohmann_json 3.2.0 REQUIRED)

# Source files
add_executable(bitpup src/main.cpp)

# Link dependencies
target_link_libraries(bitpup PRIVATE yaml-cpp nlohmann_json::nlohmann_json)

# Install to /usr/bin if needed
install(TARGETS bitpup RUNTIME DESTINATION bin)
