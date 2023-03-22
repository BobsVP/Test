cmake_minimum_required(VERSION 3.13)

project(TestCMake VERSION 1.0 
 DESCRIPTION "CMake test"
 LANGUAGES CXX)

set(SOURCES Source.cpp)

add_executable(TestCMake ${SOURCES})

#get_directory_property(IS_SUBPROJECT PARENT_DIRECTORY) #включён ли наш проект в другой проект в качестве подпроекта

#option(MYLIB_TESTING "Включить модульное тестирование" ON)

#option(MYLIB_COVERAGE "Включить измерение покрытия кода тестами" OFF)

#add_compile_options( #максимальный уровень диагностик времени компиляции
#    -Werror
#
#    -Wall
#    -Wextra
#    -Wpedantic
#
#    -Wcast-align
#    -Wcast-qual
#    -Wconversion
#    -Wctor-dtor-privacy
#    -Wenum-compare
#    -Wfloat-equal
#    -Wnon-virtual-dtor
#    -Wold-style-cast
#    -Woverloaded-virtual
#    -Wredundant-decls
#    -Wsign-conversion
#    -Wsign-promo
#)

if(NOT CMAKE_CXX_EXTENSIONS) # отключение расширений языка
    set(CMAKE_CXX_EXTENSIONS OFF)
endif()

target_include_directories(TestCMake INTERFACE
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
    $<INSTALL_INTERFACE:include>
)