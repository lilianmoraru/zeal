add_library(Registry STATIC
    docset.cpp
    docsetmetadata.cpp
    docsetregistry.cpp
    listmodel.cpp
    searchmodel.cpp
    searchquery.cpp

    # Show headers without .cpp in Qt Creator.
    cancellationtoken.h
    itemdatarole.h
    searchresult.h
)

target_link_libraries(Registry Util Qt::Concurrent Qt::Gui Qt::Network)
