# React Native Expo Turtle Build & Upload
> Developed with &hearts; and sponsored by [Polyglot](https://realpolyglot.dev) and [Happii LLC](https://apps.apple.com/us/developer/happii-llc/id1107883445).

[![Build Status](http://img.shields.io/travis/wilmoore/react-native-expo-turtle-build-and-upload.svg)](https://travis-ci.org/wilmoore/react-native-expo-turtle-build-and-upload) [![NPM downloads](http://img.shields.io/npm/dm/react-native-expo-turtle-build-and-upload.svg)](https://www.npmjs.org/package/react-native-expo-turtle-build-and-upload) [![npm](https://img.shields.io/npm/v/react-native-expo-turtle-build-and-upload.svg)](https://www.npmjs.org/package/react-native-expo-turtle-build-and-upload) ![](https://img.shields.io/badge/license-MIT-blue.svg)

[react-native-expo-turtle-build-and-upload](https://github.com/wilmoore/react-native-expo-turtle-build-and-upload) is a set of [GNU Make](https://www.gnu.org/software/make) targets for building and uploading React Native application releases for iOS and Android. It exposes a GNU Make file `build-and-upload` in the directory `node_modules/react-native-expo-turtle-build-and-upload` which you must include in your project's `makefile`.

![react-native-expo-turtle-build-and-upload](https://cloudup.com/c1uPrGUVRRj+ "react-native-expo-turtle-build-and-upload")

## Requirements
- A [React Native][React Native] application bootstrapped via [`expo init`](https://expo.io/learn).
- [Xcode Command Line Tools][Xcode Command Line Tools] (`xcode-select --install`).
- [fastlane][fastlane] (`brew install fastlane && brew link fastlane`).

## Installation & Setup
###### npm
```
npm install react-native-expo-turtle-build-and-upload --save-dev
```

###### yarn
```
yarn add react-native-expo-turtle-build-and-upload --dev
```

###### configure `app.json`
- [iOS](https://docs.expo.io/versions/latest/workflow/configuration/#ios)
- [Android](https://docs.expo.io/versions/latest/workflow/configuration/#android)

###### setup environment variables
- `CERTIFICATE_ROOT`: directory containing `ios_distribution.mobileprovision` and `ios_distribution.p12`.
- `EXPO_USERNAME`: Expo account username.
- `EXPO_PASSWORD`: Expo account password.
- `EXPO_APPLE_TEAM_ID`: Apple Team ID - (a 10-character string like `Q2DBWS92CA`).
- `EXPO_IOS_DIST_P12_PASSWORD`: iOS Distribution Certificate password.
- `IOS_APP_UPLOAD_USERNAME`: Apple Developer account username.
- `IOS_APP_UPLOAD_PASSWORD`: Apple Developer account application-specific password.
- `EXPO_SDK_VERSION`: Expo SDK version of your app.

###### add the following line to your [`makefile`](https://github.com/wilmoore/react-native-expo-turtle-build-and-upload/blob/master/makefile)
```
include node_modules/react-native-expo-turtle-build-and-upload/build-and-upload
```

## Available Targets
0. `turtle-build-ios`
0. `to-appstore`
0. `turtle-build-android`
0. `to-playstore`

## Usage
###### build `ios_distribution.ipa` for the app store
```
make turtle-build-ios
```

###### upload `ios_distribution.ipa` to the app store
```
make to-appstore
```

###### build `android_distribution.apk` for the app store
```
make turtle-build-android
```

###### upload `android_distribution.apk` to the play store
```
make to-playstore
```

## CI
#### Expo
- [Building Standalone Apps on Your CI - Expo Documentation](https://docs.expo.io/versions/latest/distribution/turtle-cli)

#### bitrise
- [Using the Generic File Storage](https://devcenter.bitrise.io/tutorials/how-to-use-the-generic-file-storage/#uploading-files-to-generic-file-storage-on-bitriseio)
- [bitrise: Build Expo apps with turtle-cli](https://discuss.bitrise.io/t/build-expo-apps-with-turtle-cli/7916/2)

## Reference
- [Including Other Makefiles][Including Other Makefiles]

## Inspiration
- [Modern Make][Modern Make]

## Alternatives
- N/A

---
[React Native]: https://reactnative.dev
[Xcode Command Line Tools]: https://developer.apple.com/library/archive/technotes/tn2339/_index.html
[Modern Make]: https://github.com/tj/mmake
[Including Other Makefiles]: https://www.gnu.org/software/make/manual/make.html#Include
