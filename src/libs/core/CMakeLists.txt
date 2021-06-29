add_library(Core STATIC
    application.cpp
    applicationsingleton.cpp
    extractor.cpp
    filemanager.cpp
    httpserver.cpp
    networkaccessmanager.cpp
    settings.cpp

    # Show headers without .cpp in Qt Creator.
    httplib.h
)

find_package(LibArchive REQUIRED)
target_link_libraries(Core PRIVATE Qt::Network Qt::WebEngine Qt::Widgets Registry Ui ${LibArchive_LIBRARIES})
target_include_directories(Core PRIVATE ${LibArchive_INCLUDE_DIRS})
target_compile_definitions(Core PRIVATE CPPHTTPLIB_USE_POLL) # Configure cpp-httplib.

# Required by cpp-httplib.
if(NOT WIN32)
    set(THREADS_PREFER_PTHREAD_FLAG ON)
    find_package(Threads REQUIRED)
    target_link_libraries(Core PRIVATE Threads::Threads)
endif()
