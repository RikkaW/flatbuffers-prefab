cmake_minimum_required(VERSION 3.4.1)

project("flatbuffers")

include_directories("include")

add_library(flatbuffers INTERFACE)
target_include_directories(flatbuffers INTERFACE include)
