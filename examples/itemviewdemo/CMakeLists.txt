set(SOURCES 
            main.cpp 
            demowidget.cpp
            qoptionmodel.cpp)

set(HEADERS 
        demowidget.h
        qoptionmodel.h)


add_executable(itemviewdemo
    ${SOURCES}
    ${HEADERS})
target_include_directories(itemviewdemo PUBLIC ../../qtwidgetsextra/include ../../qtplugins/include)
target_compile_definitions(itemviewdemo PRIVATE
        QT_DEPRECATED_WARNINGS QTWIDGETSEXTRA_DLL QTPLUGINS_DLL)
target_link_libraries(itemviewdemo Qt5::Widgets qtwidgetsextra qtplugins)