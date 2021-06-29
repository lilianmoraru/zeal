add_library(Widgets STATIC
    layouthelper.cpp
    searchedit.cpp
    shortcutedit.cpp
    toolbarframe.cpp
)

target_link_libraries(Widgets Qt::Widgets)
