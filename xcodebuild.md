---
title: XCodebuild
---

### Build

#### Build and Archive

    xcodebuild -scheme "${APPLICATION_NAME}" archive -archivePath "${APPLICATION_NAME}.xcarchive" -configuration Release || exit 1

#### Export IPA
    xcodebuild -exportArchive -exportFormat ipa -archivePath "${APPLICATION_NAME}.xcarchive" -exportPath "${APPLICATION_NAME}.ipa" -exportProvisioningProfile "${PROVISONING_PROFILE}" 


### Show Build Settings

    xcodebuild -project myProj.xcodeproj -target "myTarg" -showBuildSettings
    
    // List schemes
    xcodebuild -workspace Paltalk.xcworkspace/ -list


### XCodebuild Path

    xcode-select --print-path   # Show the path 
    
    # Switch to diff xcode
    sudo xcode-select --switch /Applications/Xcode6.4/Xcode.app
    
    ## Switch XCode Without sudo
    export DEVELOPER_DIR=/Users/wpuricz/Applications/Xcode82.app/Contents/Developer  


### Tests 
```bash
xcodebuild test -workspace KMFSampleApp.xcworkspace -scheme KMFSampleApp -destination 'platform=iOS Simulator,name=iPhone 5'
```

### Trace Swift Build Times
Before tracing, add to build settings: (Other Swift Flags): -Xfrontend -debug-time-function-bodies

```bash
xcodebuild -project OCFramework.xcodeproj -target OCFramework clean build | grep [1-9].[0-9]ms | sort -nr > culprits.txt

xcodebuild -project OCFramework.xcodeproj -target OCFramework clean build OTHER_SWIFT_FLAGS="-Xfrontend -debug-time-function-bodies" | grep .[0-9]ms | grep -v ^0.[0-9]ms | sort -nr > culprits.txt

xcodebuild -workspace App.xcworkspace -scheme App clean build | grep [1-9].[0-9]ms | sort -nr > culprits.txt
```

### Resources
[Swift Profiling](http://irace.me/swift-profiling)