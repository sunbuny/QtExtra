set(SOURCES 
                main.cpp 
        pages.cpp
        qconfigwidget.cpp
        qconfigwizard.cpp)

set(HEADERS 
        pages.h
        qconfigwidget.h
        qconfigwizard.h)


add_executable(configwidget
    ${SOURCES}
    ${HEADERS})
target_include_directories(configwidget PUBLIC ../../qtwidgetsextra/include)
target_compile_definitions(configwidget PRIVATE
        QT_DEPRECATED_WARNINGS QTWIDGETSEXTRA_DLL)
target_link_libraries(configwidget Qt5::Widgets qtwidgetsextra)