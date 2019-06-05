platform :ios, '10.2'
use_frameworks!

target 'passKit' do
    target 'pass' do
        inherit! :search_paths
    end
    target 'passExtension' do
        inherit! :search_paths
    end
    target 'passKitTests' do
        inherit! :search_paths
    end
end

post_install do |installer|
  installer.pods_project.targets.each do |target|
    target.build_configurations.each do |config|
      cflags = config.build_settings['OTHER_CFLAGS'] || ['$(inherited)']
      cflags << '-fembed-bitcode'
      config.build_settings['OTHER_CFLAGS'] = cflags
    end
  end
end
