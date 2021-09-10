# Cordova Platform devDependencies Reproduction

This is a minimal reproduction for Issue [apache/cordova-lib#866](https://github.com/apache/cordova-lib/issues/866).

## How to reproduce

```shell
npm install
npx cordova prepare android
```

## What is the problem

`package.json` contains `devDependency`: `"cordova-android": "^10.1.0"`.

However, `cordova prepare android` pulls `cordova-android@^9.0.0` (the pinned version).

```
Discovered platform "android". Adding it to the project
Using cordova-fetch for cordova-android@^9.0.0
Adding android project...
Creating Cordova project for the Android platform:
        Path: platforms\android
        Package: io.cordova.hellocordova
        Name: HelloCordova
        Activity: MainActivity
        Android target: android-29
Subproject Path: CordovaLib
Subproject Path: app
Android project created with cordova-android@9.1.0
Discovered plugin "cordova-plugin-whitelist". Adding it to the project
Installing "cordova-plugin-whitelist" for android
```

See Pull Request [apache/cordova-lib#874](https://github.com/apache/cordova-lib/pull/874) for additional context and troubleshooting info.
