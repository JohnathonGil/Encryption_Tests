cmake_minimum_required(VERSION 3.21)

project(CHATROOM_LIB)

set(SRC_FILES main.cpp)

find_package(BOOST 1.85.0 REQUIRED)

file(GLOB SOURCES src/* src/*/* src/*/*/*)
add_library(${PROJECT_NAME} ${SOURCES})

target_include_directories(${PROJECT_NAME}
        PUBLIC
            $<INSTALL_INTERFACE:include>
            $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
        PRIVATE
            ${BOOST_INCLUDE_DIRS}
)

target_link_libraries(${PROJECT_NAME}
    PRIVATE
        ${BOOST_LIBRARIES}

)