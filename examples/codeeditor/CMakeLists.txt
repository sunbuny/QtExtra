set(SOURCES 
        main.cpp 
        codeeditor.cpp 
    jsedit.cpp)

set(HEADERS 
        codeeditor.h 
    jsedit.h)

set(RESOURCES 
    codeeditor.qrc)

add_executable(codeeditor 
    ${SOURCES}
    ${HEADERS}
    ${RESOURCES})
target_include_directories(codeeditor PUBLIC ../../qtwidgetsextra/include )
target_compile_definitions(codeeditor PRIVATE
        QT_DEPRECATED_WARNINGS QTWIDGETSEXTRA_DLL)
target_link_libraries(codeeditor Qt5::Widgets qtwidgetsextra)
