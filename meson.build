project('math', 'cpp', default_options: ['cpp_std=c++20'])

pub_headers  = [include_directories('exports')]
priv_headers = [include_directories('src'), include_directories('src/lib'), include_directories('exports/math')]

libmath = library('math', 'src/lib/add2.cpp', include_directories: priv_headers)
libmath_dep = declare_dependency(include_directories: pub_headers, link_with: libmath)

main = executable('main', 'src/main.cpp', link_with: libmath, include_directories: priv_headers)

gtest_main_dep = subproject('gtest').get_variable('gtest_main_dep')
test('tests', executable('_', 'tests/add2.test.cpp',
  dependencies: gtest_main_dep,
  link_with: libmath,
  include_directories: priv_headers
))
