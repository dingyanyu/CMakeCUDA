
cmake_minimum_required(VERSION 2.8 )
project(vectorAdd)
include_directories(/usr/local/cuda-8.0/samples/common/inc)
find_package(CUDA REQUIRED)
set(PROJECT_SRC vectorAdd.cu)
set(GENCODE -gencode=arch=compute_61,code=sm_61)
set(CUDA_NVCC_FLAGS_DEBUG "-g -G")
set(CMAKE_CXX_FLAGS_DEBUG "-g")

set(CUDA_NVCC_FLAGS_RELEASE "-O2")
set(CMAKE_CXX_FLAGS_RELEASE "-O2")
cuda_add_executable(vectorAdd ${PROJECT_SRC} OPTIONS ${GENCODE})
