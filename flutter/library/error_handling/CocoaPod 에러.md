# CocoaPod 에러

2021.10.22 컴퓨터 세팅을 다시 한 후에 해당 에러가 발생하였다.

여러케이스에서 시도를 해보았다.

```swift
Launching lib/app/main.dart on iPhone 11 in debug mode...
Running pod install...
CocoaPods' output:
↳
      Preparing

    Analyzing dependencies

    Inspecting targets to integrate
      Using `ARCHS` setting to build architectures of target `Pods-Runner`: (``)

    Finding Podfile changes
      A webview_flutter_wkwebview
      R webview_flutter
      - Flutter
      - firebase_core
      - firebase_dynamic_links
      - firebase_messaging
      - flutter_inappwebview
      - flutter_local_notifications
      - fluttertoast
      - path_provider
      - share_plus
      - shared_preferences
      - sqflite
      - url_launcher

    Fetching external sources
    -> Fetching podspec for `Flutter` from `Flutter`
    -> Fetching podspec for `firebase_core` from `.symlinks/plugins/firebase_core/ios`
    firebase_core: Using Firebase SDK version '8.7.0' defined in 'firebase_core'
    -> Fetching podspec for `firebase_dynamic_links` from `.symlinks/plugins/firebase_dynamic_links/ios`
    firebase_dynamic_links: Using Firebase SDK version '8.7.0' defined in 'firebase_core'
    -> Fetching podspec for `firebase_messaging` from `.symlinks/plugins/firebase_messaging/ios`
    firebase_messaging: Using Firebase SDK version '8.7.0' defined in 'firebase_core'
    -> Fetching podspec for `flutter_inappwebview` from `.symlinks/plugins/flutter_inappwebview/ios`
    -> Fetching podspec for `flutter_local_notifications` from `.symlinks/plugins/flutter_local_notifications/ios`
    -> Fetching podspec for `fluttertoast` from `.symlinks/plugins/fluttertoast/ios`
    -> Fetching podspec for `path_provider` from `.symlinks/plugins/path_provider/ios`
    -> Fetching podspec for `share_plus` from `.symlinks/plugins/share_plus/ios`
    -> Fetching podspec for `shared_preferences` from `.symlinks/plugins/shared_preferences/ios`
    -> Fetching podspec for `sqflite` from `.symlinks/plugins/sqflite/ios`
    -> Fetching podspec for `url_launcher` from `.symlinks/plugins/url_launcher/ios`
    -> Fetching podspec for `webview_flutter_wkwebview` from `.symlinks/plugins/webview_flutter_wkwebview/ios`

    Resolving dependencies of `Podfile`

Error output from CocoaPods:
↳

    [!] Automatically assigning platform `iOS` with version `13.0` on target `Runner` because no platform was specified. Please specify a platform for this target in your Podfile. See `https://guides.cocoapods.org/syntax/podfile.html#platform`.
    /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require': dlopen(/Library/Ruby/Gems/2.6.0/gems/ffi-1.15.4/lib/ffi_c.bundle, 9): no suitable image found.  Did find: (LoadError)
    	/Library/Ruby/Gems/2.6.0/gems/ffi-1.15.4/lib/ffi_c.bundle: mach-o, but wrong architecture
    	/Library/Ruby/Gems/2.6.0/gems/ffi-1.15.4/lib/ffi_c.bundle: mach-o, but wrong architecture - /Library/Ruby/Gems/2.6.0/gems/ffi-1.15.4/lib/ffi_c.bundle
    	from /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'
    	from /Library/Ruby/Gems/2.6.0/gems/ffi-1.15.4/lib/ffi.rb:5:in `rescue in <top (required)>'
    	from /Library/Ruby/Gems/2.6.0/gems/ffi-1.15.4/lib/ffi.rb:2:in `<top (required)>'
    	from /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'
    	from /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'
    	from /Library/Ruby/Gems/2.6.0/gems/ethon-0.15.0/lib/ethon.rb:3:in `<top (required)>'
    	from /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'
    	from /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'
    	from /Library/Ruby/Gems/2.6.0/gems/typhoeus-1.4.0/lib/typhoeus.rb:2:in `<top (required)>'
    	from /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'
    	from /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/cdn_source.rb:440:in `download_typhoeus_impl_async'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/cdn_source.rb:372:in `download_and_save_with_retries_async'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/cdn_source.rb:365:in `download_file_async'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/cdn_source.rb:338:in `download_file'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/cdn_source.rb:53:in `refresh_metadata'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source.rb:31:in `initialize'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/cdn_source.rb:30:in `initialize'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:315:in `new'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:315:in `block in source_from_path'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:322:in `source_from_path'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:331:in `block in aggregate_with_repos'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:331:in `map'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:331:in `aggregate_with_repos'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:26:in `aggregate'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:60:in `all'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/user_interface/error_report.rb:173:in `repo_information'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/user_interface/error_report.rb:77:in `stack'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/user_interface/error_report.rb:24:in `report'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/command.rb:66:in `report_error'
    	from /Library/Ruby/Gems/2.6.0/gems/claide-1.0.3/lib/claide/command.rb:396:in `handle_exception'
    	from /Library/Ruby/Gems/2.6.0/gems/claide-1.0.3/lib/claide/command.rb:337:in `rescue in run'
    	from /Library/Ruby/Gems/2.6.0/gems/claide-1.0.3/lib/claide/command.rb:324:in `run'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/command.rb:52:in `run'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/bin/pod:55:in `<top (required)>'
    	from /usr/local/bin/pod:23:in `load'
    	from /usr/local/bin/pod:23:in `<main>'
    /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require': cannot load such file -- 2.6/ffi_c (LoadError)
    	from /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'
    	from /Library/Ruby/Gems/2.6.0/gems/ffi-1.15.4/lib/ffi.rb:3:in `<top (required)>'
    	from /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'
    	from /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'
    	from /Library/Ruby/Gems/2.6.0/gems/ethon-0.15.0/lib/ethon.rb:3:in `<top (required)>'
    	from /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'
    	from /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'
    	from /Library/Ruby/Gems/2.6.0/gems/typhoeus-1.4.0/lib/typhoeus.rb:2:in `<top (required)>'
    	from /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'
    	from /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/cdn_source.rb:440:in `download_typhoeus_impl_async'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/cdn_source.rb:372:in `download_and_save_with_retries_async'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/cdn_source.rb:365:in `download_file_async'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/cdn_source.rb:338:in `download_file'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/cdn_source.rb:53:in `refresh_metadata'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source.rb:31:in `initialize'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/cdn_source.rb:30:in `initialize'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:315:in `new'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:315:in `block in source_from_path'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:322:in `source_from_path'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:331:in `block in aggregate_with_repos'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:331:in `map'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:331:in `aggregate_with_repos'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:26:in `aggregate'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:60:in `all'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/user_interface/error_report.rb:173:in `repo_information'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/user_interface/error_report.rb:77:in `stack'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/user_interface/error_report.rb:24:in `report'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/command.rb:66:in `report_error'
    	from /Library/Ruby/Gems/2.6.0/gems/claide-1.0.3/lib/claide/command.rb:396:in `handle_exception'
    	from /Library/Ruby/Gems/2.6.0/gems/claide-1.0.3/lib/claide/command.rb:337:in `rescue in run'
    	from /Library/Ruby/Gems/2.6.0/gems/claide-1.0.3/lib/claide/command.rb:324:in `run'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/command.rb:52:in `run'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/bin/pod:55:in `<top (required)>'
    	from /usr/local/bin/pod:23:in `load'
    	from /usr/local/bin/pod:23:in `<main>'
    /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require': dlopen(/Library/Ruby/Gems/2.6.0/gems/ffi-1.15.4/lib/ffi_c.bundle, 9): no suitable image found.  Did find: (LoadError)
    	/Library/Ruby/Gems/2.6.0/gems/ffi-1.15.4/lib/ffi_c.bundle: mach-o, but wrong architecture
    	/Library/Ruby/Gems/2.6.0/gems/ffi-1.15.4/lib/ffi_c.bundle: mach-o, but wrong architecture - /Library/Ruby/Gems/2.6.0/gems/ffi-1.15.4/lib/ffi_c.bundle
    	from /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'
    	from /Library/Ruby/Gems/2.6.0/gems/ffi-1.15.4/lib/ffi.rb:5:in `rescue in <top (required)>'
    	from /Library/Ruby/Gems/2.6.0/gems/ffi-1.15.4/lib/ffi.rb:2:in `<top (required)>'
    	from /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'
    	from /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'
    	from /Library/Ruby/Gems/2.6.0/gems/ethon-0.15.0/lib/ethon.rb:3:in `<top (required)>'
    	from /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'
    	from /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'
    	from /Library/Ruby/Gems/2.6.0/gems/typhoeus-1.4.0/lib/typhoeus.rb:2:in `<top (required)>'
    	from /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'
    	from /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/cdn_source.rb:440:in `download_typhoeus_impl_async'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/cdn_source.rb:372:in `download_and_save_with_retries_async'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/cdn_source.rb:365:in `download_file_async'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/cdn_source.rb:338:in `download_file'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/cdn_source.rb:53:in `refresh_metadata'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source.rb:31:in `initialize'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/cdn_source.rb:30:in `initialize'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:315:in `new'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:315:in `block in source_from_path'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:322:in `source_from_path'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:331:in `block in aggregate_with_repos'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:331:in `map'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:331:in `aggregate_with_repos'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:26:in `aggregate'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:60:in `all'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:393:in `source_with_url'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/sources_manager.rb:22:in `find_or_create_source_with_url'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/installer/analyzer.rb:178:in `block in sources'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/installer/analyzer.rb:177:in `map'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/installer/analyzer.rb:177:in `sources'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/installer/analyzer.rb:1077:in `block in resolve_dependencies'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/user_interface.rb:64:in `section'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/installer/analyzer.rb:1076:in `resolve_dependencies'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/installer/analyzer.rb:124:in `analyze'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/installer.rb:416:in `analyze'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/installer.rb:241:in `block in resolve_dependencies'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/user_interface.rb:64:in `section'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/installer.rb:240:in `resolve_dependencies'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/installer.rb:161:in `install!'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/command/install.rb:52:in `run'
    	from /Library/Ruby/Gems/2.6.0/gems/claide-1.0.3/lib/claide/command.rb:334:in `run'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/command.rb:52:in `run'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/bin/pod:55:in `<top (required)>'
    	from /usr/local/bin/pod:23:in `load'
    	from /usr/local/bin/pod:23:in `<main>'
    /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require': cannot load such file -- 2.6/ffi_c (LoadError)
    	from /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'
    	from /Library/Ruby/Gems/2.6.0/gems/ffi-1.15.4/lib/ffi.rb:3:in `<top (required)>'
    	from /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'
    	from /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'
    	from /Library/Ruby/Gems/2.6.0/gems/ethon-0.15.0/lib/ethon.rb:3:in `<top (required)>'
    	from /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'
    	from /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'
    	from /Library/Ruby/Gems/2.6.0/gems/typhoeus-1.4.0/lib/typhoeus.rb:2:in `<top (required)>'
    	from /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'
    	from /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/2.6.0/rubygems/core_ext/kernel_require.rb:54:in `require'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/cdn_source.rb:440:in `download_typhoeus_impl_async'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/cdn_source.rb:372:in `download_and_save_with_retries_async'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/cdn_source.rb:365:in `download_file_async'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/cdn_source.rb:338:in `download_file'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/cdn_source.rb:53:in `refresh_metadata'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source.rb:31:in `initialize'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/cdn_source.rb:30:in `initialize'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:315:in `new'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:315:in `block in source_from_path'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:322:in `source_from_path'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:331:in `block in aggregate_with_repos'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:331:in `map'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:331:in `aggregate_with_repos'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:26:in `aggregate'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:60:in `all'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-core-1.11.2/lib/cocoapods-core/source/manager.rb:393:in `source_with_url'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/sources_manager.rb:22:in `find_or_create_source_with_url'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/installer/analyzer.rb:178:in `block in sources'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/installer/analyzer.rb:177:in `map'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/installer/analyzer.rb:177:in `sources'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/installer/analyzer.rb:1077:in `block in resolve_dependencies'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/user_interface.rb:64:in `section'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/installer/analyzer.rb:1076:in `resolve_dependencies'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/installer/analyzer.rb:124:in `analyze'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/installer.rb:416:in `analyze'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/installer.rb:241:in `block in resolve_dependencies'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/user_interface.rb:64:in `section'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/installer.rb:240:in `resolve_dependencies'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/installer.rb:161:in `install!'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/command/install.rb:52:in `run'
    	from /Library/Ruby/Gems/2.6.0/gems/claide-1.0.3/lib/claide/command.rb:334:in `run'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/lib/cocoapods/command.rb:52:in `run'
    	from /Library/Ruby/Gems/2.6.0/gems/cocoapods-1.11.2/bin/pod:55:in `<top (required)>'
    	from /usr/local/bin/pod:23:in `load'
    	from /usr/local/bin/pod:23:in `<main>'

Error running pod install
Error launching application on iPhone 11.
```

실패

```swift
flutter clean
rm -Rf ios/Pods
rm -Rf ios/.symlinks
rm -Rf ios/Flutter/Flutter.framework
rm -Rf ios/Flutter/Flutter.podspec
```

실패

```swift
/ios
pod install
```

실패 

m1 코코아팟 문제

```swift
sudo arch -x86_64 gem install ffi

Then

arch -x86_64 pod install
```

- 2021.10.22의 오류는 해당 방법으로 해결 하였음.

Solution #1 Install Pod Manually (해결)

```swift
1. Podfile.lock 을 지운다
2. cd ios로 ios로 접근한다
3. pod install을 한다
4. 설치 중에 에러가 생기면 pod install -repo -update
```

Solution #2 Install Pod automatically

```swift
1. Podfile.lock을 지운다
2. ios folder 내에 podfile을 지운다
3. Pods folder를 지운다
4. flutter clean 실행
5. 실행 후에, flutter pub get을 터미널에 입력
6. 다음에 flutter run을 터미널에 입력
```

Solution #3 Pod install

```swift
1.flutter clean
2.rm -Rf ios/Pods
3.then rm -Rf ios/.symlinks
4.rm -Rf ios/Flutter/Flutter.framework
5.rm -Rf ios/Flutter/Flutter.podspec
6.cd ios
7.pod install
8.cd ..
9.flutter build ios
10.flutter run
```

참고문서 :

[https://fluttercorner.com/error-running-pod-install-in-flutter-on-mac/](https://fluttercorner.com/error-running-pod-install-in-flutter-on-mac/)

[https://developer.apple.com/forums/thread/652822](https://developer.apple.com/forums/thread/652822)