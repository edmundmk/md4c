project( 'md4c', 'c', version : '0.4.2' )

version = meson.project_version().split( '.' )
defines = [
    '-DMD_VERSION_MAJOR=' + version[ 0 ],
    '-DMD_VERSION_MINOR=' + version[ 1 ],
    '-DMD_VERSION_RELEASE=' + version[ 2 ]
]

sources = [ 'md4c/md4c.c' ]
md4c = library( 'md4c', sources : sources, c_args : defines, install : true )
install_headers( 'md4c/md4c.h' )
md4c_dep = declare_dependency( include_directories : include_directories( 'md4c' ), link_with : md4c )

sources = [
    'md2html/cmdline.c',
    'md2html/entity.c',
    'md2html/md2html.c',
    'md2html/render_html.c'
]
md2html = executable( 'md2html', sources : sources, c_args : defines, dependencies : md4c_dep, install : true )
install_man( 'md2html/md2html.1' )
