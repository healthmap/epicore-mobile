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

Also, edit www/js/app.js file and set app_mode to mobile_dev.

```sh
var app_mode = 'mobile_dev';

```

### Add Platforms

```sh
cordova platform add ios
cordova platform add android
```

### Clone Epicore repo

Clone the Epicore web app repo into the www directory.

```sh
git clone https://github.com/healthmap/epicore.git www

```


### Test the app in the emulator

Note: each platform SDK must be installed first - see above.

Start iOS Emulator
```sh
cordova emulate ios --target='iPhone-6'

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

