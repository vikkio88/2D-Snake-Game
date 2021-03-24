cmake_minimum_required(VERSION 3.16)

project(snake)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin")

# the -I flag in gcc
include_directories(
  ${PROJECT_SOURCE_DIR}/include/
) 

set(APP_SOURCES 
  src/main.cpp
  src/AssetMan.cpp
  src/Game.cpp
  src/GameOver.cpp
  src/GamePlay.cpp
  src/MainMenu.cpp
  src/PauseGame.cpp
  src/Snake.cpp
  src/StateMan.cpp
)

# creates ./build/bin/APP
# SFML Lib installed with apt-get install sfml-dev
find_package(SFML 2.5 COMPONENTS audio graphics window system REQUIRED)

add_executable(${PROJECT_NAME} ${APP_SOURCES})
file(COPY assets DESTINATION ${CMAKE_RUNTIME_OUTPUT_DIRECTORY})
target_link_libraries(${PROJECT_NAME} sfml-audio sfml-graphics sfml-window sfml-system)
