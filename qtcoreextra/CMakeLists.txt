
set(HEADERS 
    src/qtsettingsmapper.h 
    src/qtxmlmapper.h 
    src/qtjsonmapper.h 
    src/qtresource.h 
    src/qtobjectmapper.h 
    src/qtmemorypool.h 
    src/qtcoreextra.h 
    src/qtglobalextra.h 
    src/qtmethodinvoker.h 
    src/qtjsonsettingsformat.h)


set(SOURCES
    src/qtsettingsmapper.cpp 
    src/qtxmlmapper.cpp 
    src/qtjsonmapper.cpp 
    src/qtresource.cpp 
    src/qtobjectmapper.cpp 
    src/qtmethodinvoker.cpp 
    src/qtjsonsettingsformat.cpp)

add_library(qtcoreextra
        ${SOURCES}
        ${HEADERS}
        )
target_compile_definitions(qtcoreextra PRIVATE
        QTCOREEXTRA_MAKEDLL QTCOREEXTRA_BUILD_LIB)
target_include_directories(qtcoreextra PUBLIC include )
target_link_libraries(qtcoreextra Qt5::Widgets)
