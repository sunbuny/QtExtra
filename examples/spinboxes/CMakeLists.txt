set(SOURCES 
            main.cpp
        demowidget.cpp)

set(HEADERS 
            demowidget.h)



add_executable(spinboxes
    ${SOURCES}
    ${HEADERS})
target_include_directories(spinboxes PUBLIC  
                ../../qtwidgetsextra/include 
                ../../qtcoreextra/include)
target_compile_definitions(spinboxes PRIVATE
        QT_DEPRECATED_WARNINGS QTWIDGETSEXTRA_DLL)
target_link_libraries(spinboxes Qt5::Widgets qtwidgetsextra)