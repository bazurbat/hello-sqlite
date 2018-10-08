cmake_minimum_required(VERSION 3.4)

project(hello-sqlite C)

find_package(PkgConfig REQUIRED)
pkg_check_modules(SQLITE sqlite3)

add_executable(hello-sqlite main.c)
target_include_directories(hello-sqlite PRIVATE ${SQLITE_INCLUDE_DIRS})
target_link_libraries(hello-sqlite ${SQLITE_LDFLAGS})

install(TARGETS hello-sqlite
    DESTINATION bin)
