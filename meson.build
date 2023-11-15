project('altera-stapl', 'c',
    default_options: [
      'buildtype=debugoptimized',
      'warning_level=3',
      #'werror=true',
      'c_std=gnu17',
    ],
    #version: '1.1.0',
    #meson_version: '>=1.1.0',
)

add_project_arguments('-D_GNU_SOURCE', language: 'c')
libgpiod = dependency('libgpiod')

executable('stapl',
           'altera-comp.c',
           'altera-gpio.c',
           'altera-jtag.c',
           'altera.c',
           c_args: [
             '-DLOCALSTATEDIR="@0@"'.format(get_option('localstatedir')),
             '-DSYSCONFDIR="@0@"'.format(get_option('sysconfdir'))
           ],
            dependencies: [
           libgpiod,
              ],
           install_dir: get_option('sbindir'),
           install: true)
