# include(GenerateExportHeader) include(GNUInstallDirs)

add_library(implot STATIC)
target_sources(
  implot
  PUBLIC FILE_SET
         implot_headers
         TYPE
         HEADERS
         FILES
         implot.h
         implot_internal.h
  PRIVATE implot.cpp implot_demo.cpp implot_items.cpp)
target_link_libraries(implot PRIVATE imgui::imgui)
add_library(implot::implot ALIAS implot)
install(TARGETS implot FILE_SET implot_headers)
