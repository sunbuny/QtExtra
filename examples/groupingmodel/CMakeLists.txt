set(SOURCES 
            main.cpp 
            modelwidget.cpp)

set(HEADERS 
        modelwidget.h)




add_executable(groupingmodel
    ${SOURCES}
    ${HEADERS})
target_include_directories(groupingmodel PUBLIC ../../qtwidgetsextra/include ../../qtpropertybrowser/include)
target_compile_definitions(groupingmodel PRIVATE
        QT_DEPRECATED_WARNINGS QTWIDGETSEXTRA_DLL)
target_link_libraries(groupingmodel Qt5::Widgets qtwidgetsextra qtpropertybrowser)