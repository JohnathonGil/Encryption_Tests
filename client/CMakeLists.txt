cmake_minimum_required(VERSION 3.21)

project(CHATROOM_CLIENT)

set(SRC_FILES main.cpp)
add_executable(${PROJECT_NAME} ${SRC_FILES})

target_include_directories(${PROJECT_NAME}
        PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}/../networking/include
)

target_link_libraries(${PROJECT_NAME}
        PUBLIC
            CHATROOM_LIB
)