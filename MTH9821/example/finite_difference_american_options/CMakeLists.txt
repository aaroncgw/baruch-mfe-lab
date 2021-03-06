cmake_minimum_required(VERSION 2.6)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -Wall -Wno-long-long -Wno-deprecated -pedantic")

include_directories(./ 
                    ../../options/
                    ../../lu/
                    ../../cholesky 
                    ../../band_op/
                    ../../linear_solve/
                    ../../triangular_solve/ 
                    ../../iterative_solve/
                    ../../fd/
                    ../../../../lib/eigen/)
 
# Link runTests with what we want to test and the GTest and pthread library
add_executable(runFDAmerican
               ../../options/black_scholes.cpp
               ../../lu/lu.cpp
               ../../band_op/band_mult.cpp
               ../../band_op/band_add.cpp
               ../../band_op/band_conversion.cpp
               ../../linear_solve/linear_solve.cpp
               ../../triangular_solve/triangular_solve.cpp
               ../../iterative_solve/linear_iterate.cpp
               ../../iterative_solve/sor.cpp
               ../../cholesky/cholesky.cpp
               ../../fd/updater.cpp
               ../../fd/heat_pde.cpp
               ../../fd/fd.cpp
               ./main.cpp)

