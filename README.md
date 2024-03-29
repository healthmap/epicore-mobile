# This repo has been archived

# Apache Cordova setup for Epicore

[Apached Cordova](https://cordova.apache.org/) is a mobile development framework used to deploy the Epicore web app for distribution as a mobile app.

The following must be also be installed:
- [Node.js](https://nodejs.org/)
- [iOS platform SDK](https://cordova.apache.org/docs/en/latest/guide/platforms/ios/index.html#requirements-and-support)
- [Android platform SDK](https://cordova.apache.org/docs/en/latest/guide/platforms/android/index.html#requirements-and-support)


### Install Cordova

```sh
sudo npm install -g cordova

```


### Install [cordova-icon](https://github.com/AlexDisler/cordova-icon) and [cordova-splash](https://github.com/AlexDisler/cordova-splash)

```sh
brew install imagemagic
sudo npm install cordova-icon -g
sudo npm install cordova-splash -g

```


### Clone Epicore Mobile project

This is the Cordova project for the Epicore Mobil apps.

```sh
git clone https://github.com/healthmap/epicore-mobile.git
cd epicore-mobile

```


### Add iOS and Android Platforms

```sh
cordova platform add ios
cordova platform add android
```

### Clone the Epicore web app repo into the www directory.

```sh
git clone https://github.com/healthmap/epicore.git www

```

Also, edit www/js/epicoreConfig.js file and set app_mode to mobile_dev.

epicore_config.app_mode = 'mobile_dev';

### Build the cordova app

Change back to the Cordova FNY mobile app directory (epicore-mobile)

#### Note: Need to increment the version code for android in config.xml (android-versionCode) for each new build.

Build for iOS
```sh
cordova build ios

```

Build for Android
```sh
cordova build android

```


### Test the app in the emulator

Note: each platform SDK must be installed first - see above.

Start iOS Emulator
```sh
cordova emulate ios --target='iPhone-X'

```

Start Android Emulator
```sh
cordova emulate android

```


### Run the app on iPhone

Plug in the iPhone and setup Xcode using automatic signing with a valid apple developers account.

Start Xcode, then open the project (File->Open) Epicore.xcodeproj in the directory platforms/ios/Epicore.xcodeproj

Run app
```sh
cordova run ios

```

### Run the app on Android phone

Android setup TBD

```sh
cordova run android

```

### App Icon and Splash screen

The icon.png and splash.png image files are automatically resized for the Cordova project.

Both image files must be perfectly square if you change them!!!
