cmake_minimum_required(VERSION 3.0.0)

project(io2d CXX)

set(CMAKE_CXX_STANDARD 17)

set(IO2D_LIB_SRC 
	io2d.h
	io2d_coregraphics_mac.h
    xio2d_cg_output_surfaces.h
    xio2d_cg_output_surfaces.mm
	../xio2d_cg_main.h
	../xio2d_cg_brushes.h
	../xio2d_cg_brushes.cpp
	../xio2d_cg_interop.h
	../xio2d_cg_paths.h
	../xio2d_cg_paths.cpp
	../xio2d_cg_surface_state_props.h
	../xio2d_cg_paths_figures.h
	../xio2d_cg_paths_figures.cpp
	../xio2d_cg_surfaces.h
	../xio2d_cg_surfaces.cpp
    ../xio2d_cg_gradient.cpp
    ../xio2d_cg_gradient.h
    ../xio2d_cg_colors.cpp
    ../xio2d_cg_colors.h
    ../xio2d_cg_texture.cpp
    ../xio2d_cg_texture.h
	../xio2d_cg_fps_counter.cpp
	../xio2d_cg_fps_counter.h
    ../xio2d_cg_display.cpp
    ../xio2d_cg_display.h
    ../xio2d_cg_tmplayer.cpp
    ../xio2d_cg_tmplayer.h
)

add_library(io2d_coregraphics_mac ${IO2D_LIB_SRC})

target_include_directories(io2d_coregraphics_mac PUBLIC
  ${CMAKE_CURRENT_SOURCE_DIR}
  ${CMAKE_CURRENT_SOURCE_DIR}/..
  ${CMAKE_CURRENT_SOURCE_DIR}/../..
)

target_link_libraries(io2d_coregraphics_mac "-framework Cocoa")
target_link_libraries(io2d_coregraphics_mac "-framework AppKit")
target_link_libraries(io2d_coregraphics_mac "-framework CoreServices")
target_link_libraries(io2d_coregraphics_mac "-framework CoreFoundation")
target_link_libraries(io2d_coregraphics_mac "-framework ImageIO")
target_link_libraries(io2d_coregraphics_mac "-framework CoreGraphics")
