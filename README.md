# Questions

1.  Can you confirm whether removing the below allows you to compile in addition to removing the file pointed out in the arrow and/or adjusting anything else?

- #### Removing `use_frameworks! :linkage => :static`

The source code is compilable if we remove this line. But we;re not abel to remove it, because the Firebase installation requires this config to be enabled

<img width="816" alt="Screen Shot 2023-08-22 at 08 54 00" src="https://github.com/anhkieet/react-native-medallia-demo-app/assets/11927500/a6a10f8e-62b0-4d69-a320-808eec306a00">
https://rnfirebase.io/#altering-cocoapods-to-use-frameworks


- #### Removing `the file pointed out in the arrow`

![Screen Shot 2023-08-17 at 15 01 47](https://github.com/anhkieet/react-native-medallia-demo-app/assets/11927500/41c6b521-8115-473c-b538-5955a058a2ad)


The source code is compilable if we remove the file pointed out in the arrow. But it's just a temporary fix in my  local environment where I can do a manual update. We have built an automatic deployment (CircleCI) where the deployment runs on the cloud, and you can't update manually

<img width="1673" alt="Screen Shot 2023-08-22 at 09 07 59" src="https://github.com/anhkieet/react-native-medallia-demo-app/assets/11927500/a64b89d2-12c5-44a1-bd11-2b197b1a4830">


2. Are you only seeing a compile issue for iOS? You are not seeing any issues for Android?
- Only iOS, Android was fine and worked correctly


# Problem
<img width="1512" alt="Screen Shot 2023-08-20 at 16 48 25" src="https://github.com/anhkieet/react-native-medallia-demo-app/assets/11927500/0377283a-cb12-47c6-9e92-ca7e3710209b">

iOS source code cannot compile if I set this config in the Podfile

```
use_frameworks! :linkage => :static
$RNMedalliaDigitalAsStaticFramework = true
```


# System and libraries information
```
System:
    OS: macOS 12.6.3
    CPU: (10) arm64 Apple M1 Pro
    Memory: 203.22 MB / 32.00 GB
    Shell: 5.8.1 - /bin/zsh
  Binaries:
    Node: 18.17.1 - ~/.nvm/versions/node/v18.17.1/bin/node
    Yarn: 1.22.19 - /opt/homebrew/bin/yarn
    npm: 9.6.7 - ~/.nvm/versions/node/v18.17.1/bin/npm
    Watchman: 2023.05.01.00 - /opt/homebrew/bin/watchman
  Managers:
    CocoaPods: 1.12.1 - /Users/david/.rvm/gems/ruby-2.7.4/bin/pod
  SDKs:
    iOS SDK:
      Platforms: DriverKit 22.2, iOS 16.2, macOS 13.1, tvOS 16.1, watchOS 9.1
    Android SDK:
      API Levels: 26, 28, 30, 31, 32, 33
      Build Tools: 28.0.3, 29.0.2, 30.0.2, 30.0.3, 31.0.0, 32.0.0, 32.1.0, 33.0.0
      System Images: android-23 | Google APIs Intel x86 Atom, android-32 | Google APIs ARM 64 v8a
      Android NDK: Not Found
  IDEs:
    Android Studio: 2022.1 AI-221.6008.13.2211.9619390
    Xcode: 14.2/14C18 - /usr/bin/xcodebuild
  Languages:
    Java: 11.0.11 - /usr/bin/javac
  npmPackages:
    @react-native-community/cli: Not Found
    react: 18.1.0 => 18.1.0 
    react-native: 0.70.9 => 0.70.9 
    react-native-macos: Not Found
  npmGlobalPackages:
    *react-native*: Not Found
```
