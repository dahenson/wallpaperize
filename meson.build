project('com.github.philip-scott.wallpaperize', ['vala', 'c'],
    version: '0.2.0'
)

gnome = import('gnome')
i18n = import('i18n')

conf = configuration_data()
conf.set_quoted('GETTEXT_PACKAGE', meson.project_name())
configure_file(output: 'config.h', configuration: conf)
config_h_dir = include_directories('.')

c_args = [
  '-include', 'config.h',
]

executable(
    'com.github.philip-scott.wallpaperize',
    'src/Application.vala',
    'src/Wallpaperize.vala',
    'src/Window.vala',
    c_args: c_args,
    dependencies: [
        dependency('glib-2.0'),
        dependency('gobject-2.0'),
        dependency('gtk+-3.0'),
        dependency('granite'),
    ],
    install : true
)

subdir('data')
