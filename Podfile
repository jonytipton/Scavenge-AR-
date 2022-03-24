platform :ios, '11.0'
use_frameworks!

# next block is added to wrokaround a code signing issue in Azure build pipelines,
# see https://github.com/Microsoft/azure-pipelines-tasks/issues/9984
post_install do |installer|
  installer.pods_project.targets.each do |target|
    target.build_configurations.each do |config|
      config.build_settings['EXPANDED_CODE_SIGN_IDENTITY'] = ""
      config.build_settings['CODE_SIGNING_REQUIRED'] = "NO"
      config.build_settings['CODE_SIGNING_ALLOWED'] = "NO"
    end
  end
end

target 'Scavenge[AR]' do

  # Pods for Scavenge[AR]
  pod 'AzureSpatialAnchors', '2.12.0'

  pod 'ADAL', :git => 'https://github.com/AzureAD/azure-activedirectory-library-for-objc', :tag => '2.7.7', :submodules => true
end
