foo_headers = files([
    'foo.hh',
])

install_headers(foo_headers)

# For building the library we use all headers:
inc = [ include_directories('.') ]

########################################################

if preparation
    install_headers('bar.hh')
endif
