po_dir = join_paths (meson.project_source_root (), 'po')

appdata_conf = configuration_data()
appdata_conf.set ('ARAVIS_API_VERSION', aravis_api_version)

configure_file (input: files('org.aravis.viewer.appdata.xml.in'),
		output: 'org.aravis.viewer-@0@.metainfo.xml'.format (aravis_api_version),
		configuration: appdata_conf,
		install_dir: aravis_app_data_dir)

desktop = i18n.merge_file (input: configure_file (input: files('org.aravis.viewer.desktop.in.in'),
						  output: 'org.aravis.viewer.desktop.in',
						  configuration: appdata_conf),
			   output: 'org.aravis.viewer-@0@.desktop'.format (aravis_api_version),
			   install: true,
			   install_dir: aravis_desktop_dir,
			   po_dir: po_dir,
			   type: 'desktop')
