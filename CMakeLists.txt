cmake_minimum_required(VERSION 3.28)
project(raytracer_weekend)

set(CMAKE_CXX_STANDARD 17)

add_executable(raytracer_weekend main.cpp
        vec3.h
        color.h
        ray.h
        hittable.h
        sphere.h
        hittable_list.h
        rtweekend.h
        interval.h
        camera.h
        material.h)

add_custom_target(run_raytracer
        COMMAND raytracer_weekend > image.ppm
        DEPENDS raytracer_weekend
        WORKING_DIRECTORY ${CMAKE_BINARY_DIR}
        COMMENT "Running raytracer_weekend and redirecting output to image.ppm"
)
