set(SOURCES 
            main.cpp 
            controller.cpp)

set(HEADERS 
            controller.h)


add_executable(metainvoke
    ${SOURCES}
    ${HEADERS})
target_include_directories(metainvoke PUBLIC ../../qtcoreextra/include)
target_compile_definitions(metainvoke PRIVATE
        QT_DEPRECATED_WARNINGS QTCOREEXTRA_DLL)
target_link_libraries(metainvoke Qt5::Widgets qtcoreextra qtpropertybrowser)