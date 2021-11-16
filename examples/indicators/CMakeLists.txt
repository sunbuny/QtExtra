set(SOURCES 
            main.cpp 
            widget.cpp)

set(HEADERS 
        widget.h)




add_executable(indicators
    ${SOURCES}
    ${HEADERS})
target_include_directories(indicators PUBLIC ../../qtwidgetsextra/include 
                                                ../../qtpropertybrowser/include
                                                ../../qtcoreextra/include)
target_compile_definitions(indicators PRIVATE
        QT_DEPRECATED_WARNINGS QTWIDGETSEXTRA_DLL)
target_link_libraries(indicators Qt5::Widgets qtwidgetsextra qtpropertybrowser)