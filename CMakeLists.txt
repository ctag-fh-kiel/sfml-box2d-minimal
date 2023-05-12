cmake_minimum_required(VERSION 3.26)
project(sfml_box2d_minimal)

set(CMAKE_CXX_STANDARD 17)
find_package(PkgConfig REQUIRED)

# Find SFML
PKG_SEARCH_MODULE(SFML REQUIRED sfml-all)
#message(FATAL_ERROR ${SFML_LIBRARIES})

INCLUDE_DIRECTORIES(${SFML_INCLUDE_DIRS} )

# Find Box2D
find_package(Box2D REQUIRED)

add_executable(sfml_box2d_minimal main.cpp)
target_link_libraries(sfml_box2d_minimal ${SFML_LIBRARIES} box2d::box2d)