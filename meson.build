project('Dear ImGUI', 'cpp', default_options: ['default_library=static'])

add_project_arguments('-DIMGUI_IMPL_OPENGL_ES2', language: 'cpp')
if target_machine.system() == 'windows'
  add_project_arguments('-DIMGUI_IMPL_OPENGL_LOADER_CUSTOM', language: 'cpp')
endif

imgui_inc = include_directories('./backends', '.')

deps = [
  dependency('sdl2'),
  dependency('threads'),
]

sources = [
  'imgui.cpp',
  'imgui_draw.cpp',
  'imgui_tables.cpp',
  'imgui_demo.cpp',
  'imgui_widgets.cpp',
  './backends/imgui_impl_sdl2.cpp',
  # './backends/imgui_impl_sdlrenderer2.cpp',
  './backends/imgui_impl_opengl3.cpp',
]

lib_imgui = library('ImGUI', sources, include_directories: imgui_inc, dependencies: deps)
lib_imgui_dep = declare_dependency(link_with: lib_imgui, include_directories: imgui_inc)
meson.override_dependency('imgui', lib_imgui_dep)