project(qt_tstfrm)

set(SRC
  test_main_loop.hpp
  test_main_loop.cpp
)

omim_add_library(${PROJECT_NAME} ${SRC})

target_compile_options(${PROJECT_NAME}
  PRIVATE
    $<$<CXX_COMPILER_ID:AppleClang,Clang>:-Wno-shorten-64-to-32>
    -Wno-deprecated-declarations
)

target_link_libraries(${PROJECT_NAME}
  Qt5::Core
  Qt5::Widgets
)