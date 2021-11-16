set(SOURCES 
            main.cpp 
            mainwindow.cpp)

set(HEADERS 
            mainwindow.h)


add_executable(objecttree
    ${SOURCES}
    ${HEADERS})
target_include_directories(objecttree PUBLIC ../../qtcoreextra/include
                                               ../../qtpropertybrowser/include)
target_compile_definitions(objecttree PRIVATE
        QT_DEPRECATED_WARNINGS QTWIDGETSEXTRA_DLL)
target_link_libraries(objecttree Qt5::Widgets qtwidgetsextra)