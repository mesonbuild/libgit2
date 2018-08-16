conf_data = configuration_data()
cc = meson.get_compiler('c')
if cc.sizeof('void*') == 8
	conf_data.set('GIT_ARCH_64', 1)
elif cc.sizeof('void*') == 4
	conf_data.set('GIT_ARCH_32', 1)
else
	error('Unsupported architecture (pointer size is ' + cc.sizeof('void*') + ' bytes)')
endif
conf_data.set('GIT_THREADS', 1)

conf_file = configure_file(
	output: 'features.h',
	configuration: conf_data,
	install_dir: 'include/git2/sys'
)
