project(timeOptKunz)

find_package(Eigen REQUIRED)
find_package(GTest REQUIRED)

add_executable(timeOptKunzTest
  Test.cpp)

add_library(timeOptKunz SHARED
  Trajectory.cpp
  Path.cpp)

include_directories(${GTEST_INCLUDE_DIRS})

target_link_libraries(timeOptKunzTest
  ${GTEST_LIBRARIES}
  timeOptKunz)

include_directories(${EIGEN_INCLUDE_DIRS})
