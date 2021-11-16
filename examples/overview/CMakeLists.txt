set(SOURCES 
            main.cpp
        mainwindow.cpp
    qtcodewindow.cpp
    qtfilesystemwindow.cpp)

set(HEADERS 
             mainwindow.h
    qtcodewindow.h
    qtfilesystemwindow.h)



add_executable(overview
    ${SOURCES}
    ${HEADERS})
target_include_directories(overview PUBLIC  ../../qtwidgetsextra/include)
target_compile_definitions(overview PRIVATE
        QT_DEPRECATED_WARNINGS QTWIDGETSEXTRA_DLL)
target_link_libraries(overview Qt5::Widgets qtwidgetsextra)