set(SOURCES 
            main.cpp 
            widget.cpp)

set(HEADERS 
            widget.h)

set(RESOURCES resources.qrc)


add_executable(messagelog
    ${SOURCES}
    ${HEADERS}
    ${RESOURCES})
target_include_directories(messagelog PUBLIC ../../qtwidgetsextra/include ../../qtplugins/include)
target_compile_definitions(messagelog PRIVATE
        QT_DEPRECATED_WARNINGS QTWIDGETSEXTRA_DLL QT_QTPROPERTYBROWSER_IMPORT)
target_link_libraries(messagelog Qt5::Widgets qtwidgetsextra qtpropertybrowser)