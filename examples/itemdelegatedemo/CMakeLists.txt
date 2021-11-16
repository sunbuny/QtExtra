set(SOURCES 
            main.cpp 
            mainwindow.cpp
            treeitem.cpp
            treemodel.cpp)

set(HEADERS 
        mainwindow.h
        treeitem.h
        treemodel.h)

set(RESOURCES itemdelegatedemo.qrc)


add_executable(itemdelegatedemo
    ${SOURCES}
    ${HEADERS}
    ${RESOURCES})
target_include_directories(itemdelegatedemo PUBLIC ../../qtwidgetsextra/include)
target_compile_definitions(itemdelegatedemo PRIVATE
        QT_DEPRECATED_WARNINGS QTWIDGETSEXTRA_DLL)
target_link_libraries(itemdelegatedemo Qt5::Widgets qtwidgetsextra)