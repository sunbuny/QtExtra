set(SOURCES 
                main.cpp 
        widget.cpp)

set(HEADERS 
        widget.h)

set(RESOURCES 
    colorpalette.qrc)

add_executable(colorpalette 
    ${SOURCES}
    ${HEADERS}
    ${RESOURCES})
target_include_directories(colorpalette PUBLIC ../../qtwidgetsextra/include )
target_compile_definitions(colorpalette PRIVATE
        QT_DEPRECATED_WARNINGS QTWIDGETSEXTRA_DLL)
target_link_libraries(colorpalette Qt5::Widgets qtwidgetsextra)