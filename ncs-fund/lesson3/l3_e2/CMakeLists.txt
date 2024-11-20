cmake_minimum_required(VERSION 3.20.0) # If the version for C make is too old the build will fail 
find_package(Zephyr REQUIRED HINTS $ENV{ZEPHYR_BASE}) # Pull in the zephyr build systems wich create a CMake target named app
project(hello_world) # Project name 

target_sources(app PRIVATE src/main.c) # add sources files for the project
target_sources_ifdef(CONFIG_MYFUNCTION app PRIVATE src/myfunction.c) # add myfunction as source for the project
