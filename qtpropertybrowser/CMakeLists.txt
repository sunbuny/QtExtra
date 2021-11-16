set(SOURCES  src/qtpropertybrowser.cpp
        src/qtpropertymanager.cpp
        src/qteditorfactory.cpp
        src/qtvariantproperty.cpp
        src/qttreepropertybrowser.cpp
        src/qtbuttonpropertybrowser.cpp
        src/qtgroupboxpropertybrowser.cpp
        src/qtpropertybrowserutils.cpp
        src/qpropertyproxyobject.cpp
    src/qtpropertywidget.cpp
    src/qtattributeresource.cpp)
        
set(HEADERS  src/qtpropertybrowser.h
        src/qtpropertymanager.h
        src/qteditorfactory.h
        src/qtvariantproperty.h
        src/qttreepropertybrowser.h
        src/qtbuttonpropertybrowser.h
        src/qtgroupboxpropertybrowser.h
        src/qtpropertybrowserutils_p.h
    src/qtpropertyproxyobject.h
    src/qtpropertywidget.h
    src/qtattributeresource.h)

set(RESOURCES  qtpropertybrowser.qrc)

add_library(qtpropertybrowser
        ${SOURCES}
        ${HEADERS}
        ${RESOURCES}
        )
target_include_directories(qtpropertybrowser PUBLIC include )
target_link_libraries(qtpropertybrowser Qt5::Widgets)