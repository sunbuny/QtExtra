set(SOURCES 
                main.cpp 
        demowidget.cpp)

set(HEADERS 
        demowidget.h)


add_executable(colorwidgets
    ${SOURCES}
    ${HEADERS})
target_include_directories(colorwidgets PUBLIC ../../qtwidgetsextra/include 
                                          ../../qtcoreextra/include)
target_compile_definitions(colorwidgets PRIVATE
        QT_DEPRECATED_WARNINGS QTWIDGETSEXTRA_DLL)
target_link_libraries(colorwidgets Qt5::Widgets qtwidgetsextra)