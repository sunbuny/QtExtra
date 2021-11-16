set(SOURCES 
            main.cpp
        widget.cpp)

set(HEADERS 
           widget.h)



add_executable(variantmodel
    ${SOURCES}
    ${HEADERS})
target_include_directories(variantmodel PUBLIC  
                ../../qtwidgetsextra/include)
target_compile_definitions(variantmodel PRIVATE
        QT_DEPRECATED_WARNINGS QTWIDGETSEXTRA_DLL QTPLUGINS_DLL)
target_link_libraries(variantmodel Qt5::Widgets qtwidgetsextra)