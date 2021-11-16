set(SOURCES 
            main.cpp 
            progresswidget.cpp)

set(HEADERS 
            progresswidget.h)

set(RESOURCES 
    multiprogress.qrc)


add_executable(multiprogress
    ${SOURCES}
    ${HEADERS}
    ${RESOURCES})
target_include_directories(multiprogress PUBLIC ../../qtwidgetsextra/include)
target_compile_definitions(multiprogress PRIVATE
        QT_DEPRECATED_WARNINGS QTWIDGETSEXTRA_DLL)
target_link_libraries(multiprogress Qt5::Widgets qtwidgetsextra)