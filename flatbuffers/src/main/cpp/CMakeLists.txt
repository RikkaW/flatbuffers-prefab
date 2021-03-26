cmake_minimum_required(VERSION 3.4.1)

project("flatbuffers")

include_directories("include")

# prefabPublishing does not support header only lib
# https://issuetracker.google.com/issues/173348031

#add_library(flatbuffers INTERFACE)
#target_include_directories(flatbuffers INTERFACE include)

add_library(flatbuffers STATIC dummy.cpp)
target_link_libraries(flatbuffers)