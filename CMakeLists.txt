cmake_minimum_required(VERSION 3.15)

project(sycl-sandbox LANGUAGES CXX)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_EXPORT_COMPILE_COMMANDS True)
# Find SYCL package
find_package(IntelSYCL REQUIRED)
# SYCL compiler (e.g., dpcpp, clang++, etc.) has to be specified from command line as:
# cmake -B build -DCMAKE_CXX_COMPILER=icpx
# Can this be changed here?

# Add SYCL source
add_executable(hello src/hello.cpp)
# link SYCL
target_link_libraries(hello IntelSYCL::SYCL_CXX)

add_executable(check_devices src/check_devices.cpp)
target_link_libraries(check_devices IntelSYCL::SYCL_CXX)
