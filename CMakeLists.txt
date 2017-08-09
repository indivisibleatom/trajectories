project(timeOptKunz)

find_package(GTest REQUIRED)
find_package(Eigen REQUIRED)

add_executable(timeOptKunzTest
  Test.cpp)

add_library(timeOptKunz SHARED
  Trajectory.cpp
  Path.cpp)

target_include_directories(timeOptKunz PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

include_directories(${GTEST_INCLUDE_DIRS})
include_directories(${EIGEN_INCLUDE_DIRS})

target_link_libraries(timeOptKunzTest
  ${GTEST_LIBRARIES}
  timeOptKunz)

