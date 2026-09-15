cmake_minimum_required(VERSION 3.20)
project(demo_api_scalar_galaxy_cpp VERSION 0.2.0 LANGUAGES CXX) # x-release-please-version

option(SCALAR_SDK_BUILD_TESTS "Build generated SDK smoke tests" OFF)

add_library(demo_api_scalar_galaxy_cpp)
add_library(demo_api_scalar_galaxy_cpp::demo_api_scalar_galaxy_cpp ALIAS demo_api_scalar_galaxy_cpp)

target_sources(demo_api_scalar_galaxy_cpp
  PRIVATE
    src/client.cpp
    src/resources/planets.cpp
    src/resources/celestial_bodies.cpp
    src/resources/authentication.cpp
)

target_include_directories(demo_api_scalar_galaxy_cpp
  PUBLIC
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
    $<INSTALL_INTERFACE:include>
)

target_compile_features(demo_api_scalar_galaxy_cpp PUBLIC cxx_std_20)

if(SCALAR_SDK_BUILD_TESTS)
  enable_testing()
  add_executable(scalar_sdk_smoke tests/smoke.cpp)
  target_link_libraries(scalar_sdk_smoke PRIVATE demo_api_scalar_galaxy_cpp)
  add_test(NAME scalar_sdk_smoke COMMAND scalar_sdk_smoke)
endif()
