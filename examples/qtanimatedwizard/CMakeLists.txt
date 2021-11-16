set(SOURCES 
            main.cpp)





add_executable(qtanimatedwizard
    ${SOURCES})
target_include_directories(qtanimatedwizard PUBLIC  ../../qtwidgetsextra/include)
target_compile_definitions(qtanimatedwizard PRIVATE
        QT_DEPRECATED_WARNINGS QTWIDGETSEXTRA_DLL)
target_link_libraries(qtanimatedwizard Qt5::Widgets qtwidgetsextra)