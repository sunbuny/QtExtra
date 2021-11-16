set(SOURCES 
            main.cpp 
            widget.cpp)

set(HEADERS 
        widget.h)

set(RESOURCES
    curvedtext.qrc)


add_executable(curvedtext
    ${SOURCES}
    ${HEADERS}
    ${RESOURCES})
target_include_directories(curvedtext PUBLIC ../../qtwidgetsextra/include ../../qtpropertybrowser/include)
target_compile_definitions(curvedtext PRIVATE
        QT_DEPRECATED_WARNINGS QTWIDGETSEXTRA_DLL)
target_link_libraries(curvedtext Qt5::Widgets qtwidgetsextra qtpropertybrowser)