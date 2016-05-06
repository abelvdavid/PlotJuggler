
include_directories( ../qwt/src ../common ../color_widgets/include)

QT5_ADD_RESOURCES (RES_SRC  resource.qrc)

QT5_WRAP_UI ( UI_SRC
    mainwindow.ui
    removecurvedialog.ui
    busydialog.ui
    curvecolorpick.ui
    )

SET( PLOTTER_SRC
    main.cpp
    mainwindow.cpp
    plotwidget.cpp
    plotmatrix.cpp
    removecurvedialog.cpp
    plotmagnifier.cpp
    busydialog.cpp
    busytaskdialog.cpp
    customtracker.cpp
    curvecolorpick.cpp
    plotdata_qwt.cpp

    )

add_executable(SuperPlotter ${PLOTTER_SRC} ${RES_SRC} ${UI_SRC})

target_link_libraries(SuperPlotter
    ${Qt5Widgets_LIBRARIES}
    ${Qt5PrintSupport_LIBRARIES}
    ${Qt5Xml_LIBRARIES}
    ${Qt5Concurrent_LIBRARIES}
    ${Qt5Core_QTMAIN_LIBRARIES}
    common
    colorwidgets
    qwt_static
    )