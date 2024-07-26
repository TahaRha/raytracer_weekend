cmake_minimum_required(VERSION 3.28)
project(raytracer_weekend)

set(CMAKE_CXX_STANDARD 17)

include_directories(include)

add_executable(raytracer_weekend main.cpp)

add_custom_target(run_raytracer
        COMMAND raytracer_weekend > image.ppm
        DEPENDS raytracer_weekend
        WORKING_DIRECTORY ${CMAKE_BINARY_DIR}
        COMMENT "Running raytracer_weekend and redirecting output to image.ppm"
)
