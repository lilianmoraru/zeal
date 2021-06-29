add_library(Sidebar STATIC
    container.cpp
    proxyview.cpp
    view.cpp
    viewprovider.cpp
)
target_link_libraries(Sidebar PRIVATE Qt::Widgets)
