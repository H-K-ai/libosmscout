styleeditorSrc = [
  'src/MainWindow.cpp',
  'src/SettingsDialog.cpp',
  'src/FileIO.cpp',
  'src/Highlighter.cpp',
  'src/StyleEditor.cpp',
  'src/StyleAnalyser.cpp'
]

styleeditorIncDir = include_directories('src')

styleeditorMocs = qt5.preprocess(moc_headers : [
                                    'src/MainWindow.h',
                                    'src/SettingsDialog.h',
                                    'src/FileIO.h',
                                    'src/Highlighter.h',
                                    'src/StyleAnalyser.h'
                                    ],
                                 include_directories: include_directories('src'),
                                 qresources: ['StyleEditor.qrc'])

OSMScout2 = executable('StyleEditor',
                       styleeditorSrc,
                       styleeditorMocs,
                       cpp_args: ['-fPIC'],
                       include_directories: [styleeditorIncDir, osmscoutclientqtIncDir, osmscoutmapqtIncDir, osmscoutmapIncDir, osmscoutIncDir],
                       dependencies: [mathDep, openmpDep, qt5GuiDep, qt5WidgetsDep, qt5QmlDep, qt5QuickDep, qt5SvgDep, qt5NetworkDep, qt5LocationDep, qt5MultimediaDep],
                       link_with: [osmscoutclientqt, osmscoutmapqt, osmscoutmap, osmscout],
                       install: true)

