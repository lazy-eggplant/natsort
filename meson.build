project('natsort', 'c', version: '1.0.0')

src = files('./src/strnatcmp.c')

include_dir = include_directories('./include')

natsort = library(
    'natsort',
    src,
    include_directories: [include_dir],
    install: not meson.is_subproject(),
)
natsort_dep = declare_dependency(
    include_directories: include_dir,
    link_with: natsort,
)

pkg_mod = import('pkgconfig')

pkg_mod.generate(
    natsort,
    name: 'natsort',
    description: 'Natural string sorting',
    libraries: natsort,
    version: meson.project_version(),
)
