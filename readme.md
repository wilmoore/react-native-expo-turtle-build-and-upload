# React Native Expo Turtle Build & Upload
> Developed with &hearts; and sponsored by [Polyglot](https://realpolyglot.dev) and [Happii LLC](https://apps.apple.com/us/developer/happii-llc/id1107883445).

[![Build Status](http://img.shields.io/travis/wilmoore/react-native-expo-turtle-build-and-upload.svg)](https://travis-ci.org/wilmoore/react-native-expo-turtle-build-and-upload) [![NPM downloads](http://img.shields.io/npm/dm/react-native-expo-turtle-build-and-upload.svg)](https://www.npmjs.org/package/react-native-expo-turtle-build-and-upload) [![npm](https://img.shields.io/npm/v/react-native-expo-turtle-build-and-upload.svg)](https://www.npmjs.org/package/react-native-expo-turtle-build-and-upload) ![](https://img.shields.io/badge/license-MIT-blue.svg)

[react-native-expo-turtle-build-and-upload](https://github.com/wilmoore/react-native-expo-turtle-build-and-upload) is a set of [GNU Make](https://www.gnu.org/software/make) targets for building and uploading React Native application releases for iOS and Android. It exposes a GNU Make file `build-and-upload` in the directory `node_modules/react-native-expo-turtle-build-and-upload` which you must include in your project's `makefile`.

![react-native-expo-turtle-build-and-upload](https://cloudup.com/csUwT_t3u7x+ "react-native-expo-turtle-build-and-upload")

## Requirements
- A [React Native][React Native] application bootstrapped via [`expo init`](https://expo.io/learn).
- [Xcode Command Line Tools][Xcode Command Line Tools] (`xcode-select --install`).

## Installation & Setup
###### npm
```
npm install react-native-expo-turtle-build-and-upload --save-dev
```

###### yarn
```
yarn add react-native-expo-turtle-build-and-upload --dev
```

###### environment variables
- `CERTIFICATE_ROOT`
- `LC_ALL`
- `LANG`
- `RELEASE_CHANNEL`
- `EXPO_USERNAME`
- `EXPO_PASSWORD`
- `EXPO_APPLE_TEAM_ID`
- `EXPO_IOS_DIST_P12_PASSWORD`
- `IOS_APP_UPLOAD_USERNAME`
- `IOS_APP_UPLOAD_PASSWORD`
- `EXPO_SDK_VERSION`

###### add the following line to your `makefile`
```
include build-and-upload
```

In order for `include build-and-upload` to work, the `I dir` or `--include-dir=dir` option must be used or the `build-and-upload` file must be located in the `(prefix)/include` directory which is `/usr/local/include` by default.

```
make -I node_modules/react-native-expo-turtle-build-and-upload [ targets ] ...
```

## Usage
###### build `ios_distribution.ipa` for the app store
```
make -I node_modules/react-native-expo-turtle-build-and-upload turtle-ios-build
```

###### upload `ios_distribution.ipa` to the app store
```
make -I node_modules/react-native-expo-turtle-build-and-upload to-appstore
```

## Available Targets
- `turtle-ios-build`
- `to-appstore`

## Reference
- [3.3 Including Other Makefiles][3.3 Including Other Makefiles]

## Inspiration
- [Modern Make][Modern Make]

## Alternatives
- N/A

---
[React Native]: https://reactnative.dev
[Xcode Command Line Tools]: https://developer.apple.com/library/archive/technotes/tn2339/_index.html
[Modern Make]: https://github.com/tj/mmake
[3.3 Including Other Makefiles]: https://www.gnu.org/software/make/manual/make.html#Include
