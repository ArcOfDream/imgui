project('Dear ImGUI', 'cpp', default_options: ['default_library=static'])

imgui_inc = include_directories('./backends', '.')

# subproject('glfw')
# glfwDep = dependency('glfw')
# gl = dependency('gl')
deps = [
  dependency('sdl2'),
  dependency('SDL2_image'),
  dependency('gl'),
  dependency('threads'),
]

sources = [
    'imgui.cpp',
    'imgui_draw.cpp',
    'imgui_tables.cpp',
    'imgui_demo.cpp',
    'imgui_widgets.cpp',
    './backends/imgui_impl_sdl2.cpp',
    './backends/imgui_impl_sdlrenderer2.cpp',
    './backends/imgui_impl_opengl3.cpp',
]

lib_imgui = library('ImGUI', sources, include_directories: imgui_inc, dependencies: deps)
lib_imgui_dep = declare_dependency(link_with: lib_imgui, include_directories: imgui_inc)
meson.override_dependency('imgui', lib_imgui_dep)