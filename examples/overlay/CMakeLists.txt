set(SOURCES 
            main.cpp 
            widget.cpp)

set(HEADERS 
            widget.h)



add_executable(overlay
    ${SOURCES}
    ${HEADERS})
target_include_directories(overlay PUBLIC  ../../qtwidgetsextra/include)
target_compile_definitions(overlay PRIVATE
        QT_DEPRECATED_WARNINGS QTWIDGETSEXTRA_DLL)
target_link_libraries(overlay Qt5::Widgets qtwidgetsextra)