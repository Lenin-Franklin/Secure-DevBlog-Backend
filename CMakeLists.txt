cmake_minimum_required(VERSION 3.10)
project(DevBlogAuth)

set(CMAKE_CXX_STANDARD 17)

# Include project headers
include_directories(src)

# 🔥 PostgreSQL include path (adjust version if needed)
include_directories("C:/Program Files/PostgreSQL/18/include")

# 🔥 PostgreSQL library path
link_directories("C:/Program Files/PostgreSQL/18/lib")

# Collect all source files
file(GLOB_RECURSE SOURCES
    src/*.cpp
)

# Create executable
add_executable(DevBlogAuth ${SOURCES})

# 🔥 Link PostgreSQL
target_link_libraries(DevBlogAuth libpq ws2_32)