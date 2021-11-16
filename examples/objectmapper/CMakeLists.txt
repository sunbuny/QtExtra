set(SOURCES 
            main.cpp 
            dialog.cpp)

set(HEADERS 
            dialog.h)


add_executable(objectmapper
    ${SOURCES}
    ${HEADERS})
target_include_directories(objectmapper PUBLIC ../../qtcoreextra/include
                                               ../../qtpropertybrowser/include)
target_compile_definitions(objectmapper PRIVATE
        QT_DEPRECATED_WARNINGS QT_QTPROPERTYBROWSER_IMPORT QTCOREEXTRA_DLL)
target_link_libraries(objectmapper Qt5::Widgets qtpropertybrowser qtcoreextra)