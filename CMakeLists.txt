cmake_minimum_required(VERSION 2.8)

include("cmake/HunterGate.cmake")
set(HUNTER_USE_CACHE_SERVERS NO)
HunterGate(
  URL "https://github.com/NeroBurner/hunter/archive/eigen_3.3.1.zip"
  SHA1 d6183f69f9b7f5e6f72a977238c63204a3f847b5
)
project(hunter_test_eigen_download)

hunter_add_package(Eigen)
add_executable(eigen_test main.cpp)
find_package(Eigen3 REQUIRED)
target_link_libraries(eigen_test PRIVATE Eigen3::Eigen)

