set(HEADERS  src/qtplugininterface.h 
           src/qtpluginmanager.h 
           src/qtpluginmanagerdialog.h 
           src/qtpluginmetadata.h 
           src/qtpluginpropertymodel.h 
           src/qtplugintreeview.h 
           src/qtpluginsextra.h)
set(SOURCES  src/qtplugininterface.cpp 
           src/qtpluginmanager.cpp 
           src/qtpluginmanagerdialog.cpp 
           src/qtpluginpropertymodel.cpp 
           src/qtplugintreeview.cpp)

add_library(qtplugins
        ${SOURCES}
        ${HEADERS}
        )
target_compile_definitions(qtplugins PRIVATE
        QTPLUGINS_MAKEDLL QTPLUGINS_BUILD_LIB)
target_include_directories(qtplugins PUBLIC include )
target_link_libraries(qtplugins Qt5::Widgets)
