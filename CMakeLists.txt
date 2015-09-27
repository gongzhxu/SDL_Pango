cmake_minimum_required(VERSION 2.8)

project(SDL_Pango)

include(FindPkgConfig)

pkg_search_module(SDL2 REQUIRED sdl2)
pkg_search_module(Pango REQUIRED pango)
pkg_search_module(Freetype2 REQUIRED freetype2)
pkg_search_module(Pangoft2 REQUIRED pangoft2)

add_library(SDL_Pango STATIC "SDL_Pango.c")

include_directories(${SDL2_INCLUDE_DIRS}
                    ${Pango_INCLUDE_DIRS}
                    ${Freetype2_INCLUDE_DIRS}
                    ${Pangoft2_INCLUDE_DIRS})

add_executable(example "example.c")

target_link_libraries(SDL_Pango
                      ${SDL2_LIBRARIES}
                      ${Pango_LIBRARIES}
                      ${Freetype2_LIBRARIES}
                      ${Pangoft2_LIBRARIES})

target_link_libraries(example
                      SDL_Pango
                      ${SDL2_LIBRARIES})