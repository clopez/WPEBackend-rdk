find_package(Wayland REQUIRED)
find_package(WaylandEGL REQUIRED)
find_package(WaylandEGLClient REQUIRED)

add_definitions(-DBACKEND_COMPOSITOR_CLIENT=1)
add_definitions(-DEGL_EGLEXT_PROTOTYPES=1)

list(APPEND WPE_PLATFORM_INCLUDE_DIRECTORIES
    ${WAYLAND_INCLUDE_DIRS}
    ${WAYLAND_EGL_INCLUDE_DIRS}
    ${WAYLAND_EGL_CLIENT_INCLUDE_DIRS}
)

list(APPEND WPE_PLATFORM_LIBRARIES
    ${WAYLAND_LIBRARIES}
    ${WAYLAND_EGL_LIBRARIES}
    ${WAYLAND_EGL_CLIENT_LIBRARIES}
)

list(APPEND WPE_PLATFORM_SOURCES
    src/wpeframework/renderer-backend.cpp
    src/wpeframework/view-backend.cpp
    src/wpeframework/display.cpp
)
