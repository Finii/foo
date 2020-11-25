sources = [ 'foo.cc', ]

libfoo = both_libraries('foo',
    sources,
    dependencies : deps,
    soversion : meson.project_version(),
    include_directories : inc,
    install : true,
)

foo_dep = declare_dependency(
    link_with : libfoo,
    include_directories : inc,
    dependencies : deps,
)

pkg = import('pkgconfig')
pkg.generate(libfoo,
    name : 'foo',
    description : 'An example library',
    version : meson.project_version(),
    libraries : [ '-Wl,-rpath,${libdir}' ],
    libraries_private : deps,
)

########################################################

if preparation
    libbar = shared_library('bar', 'bar.cc',
        soversion : '47.11',
        include_directories : inc,
        install : true,
    )
    pkg.generate(libbar,
        name : 'bar',
        description : 'Another example library',
        version : '47.11',
        libraries : [ '-Wl,-rpath,${libdir}' ],
    )
endif
