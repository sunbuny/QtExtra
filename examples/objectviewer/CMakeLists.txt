set(SOURCES 
            main.cpp 
            dialog.cpp)

set(HEADERS 
            dialog.h)

set(RESOURCES
    objectviewer.qrc)


add_executable(objectviewer
    ${SOURCES}
    ${HEADERS}
    ${RESOURCES})
target_include_directories(objectviewer PUBLIC ../../qtpropertybrowser/include)
target_compile_definitions(objectviewer PRIVATE
        QT_DEPRECATED_WARNINGS QT_QTPROPERTYBROWSER_IMPORT)
target_link_libraries(objectviewer Qt5::Widgets qtpropertybrowser)