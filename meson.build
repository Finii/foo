project('foo', 'cpp',
    version : '0.8.15',
    default_options : [
        'prefix=/tmp/special',
        'libdir=dir',
    ],
    meson_version : '>=0.49'
)

preparation = true

deps = dependency('bar', required : not preparation)

subdir('include')
subdir('src')

if not preparation
    subdir('tests')
endif
