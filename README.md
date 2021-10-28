## FireBase Project Setup
- Go to [Firebase](https://firebase.google.com) & create a new project(select google analytics or not => your wish)

### Android Portion Setup overview
- Select android icon
- For Creating package you will need to give the package name(Go to android manifest and copy the package name), app nickname (your wish), & SHA1 key.
- For creating the SHA1 key you need to follow these rules :
  - Go to the folder (C drive => Program Files => Java => jre => bin) => like this(C:\Program Files\Java\jre1.8.0_281\bin)
  - right click on the mouse & start the terminal 
  - right the below command & you get the two codes (SHA1 & SHA256)
  ```
  .\keytool -list -v -keystore "C:\Users\ACER\.android\debug.keystore" -alias androiddebugkey -storepass android -keypass android
  ```
  N.B : Here ACER is your pc name.
- Download the google-services.json file & paste into the app folder. => like this(\android\app\google-services.json)
- Now add the firebase sdk inside the project
  - go to => \android\build.gradle => & then paste the following codes inside the dependencies section
  ```
  // Add the following line:
  classpath 'com.google.gms:google-services:4.3.10'  // Google Services plugin
  ```
  - go to => \android\app\build.gradle => & then paste the one line code(1st code base is original structure & 2nd code base show where code to be paste & what is to be paste)
  ```
  apply plugin: 'com.android.application'
  // here is the place where new code is to be paste
  apply plugin: 'kotlin-android'
  ```
  ```
  apply plugin: 'com.android.application'
  apply plugin: 'com.google.gms.google-services'
  apply plugin: 'kotlin-android'
  ```
  - go to => \android\app\build.gradle => & then paste the following codes inside the dependencies section
  ```
  implementation platform('com.google.firebase:firebase-bom:28.4.2')
  implementation 'com.google.firebase:firebase-analytics-ktx'
  ```
  N.B : If you use kotlin as a native language then use the above code .But if you use java as a native language then use the following code
  ```
  implementation platform('com.google.firebase:firebase-bom:28.4.2')
  implementation 'com.google.firebase:firebase-analytics'
  ```
  
  ### Open the Feature of phone authentication
  - follow the steps for get the options
  - click on project overview => Authentication, then enable the phone authentication option & save

## Integrate Firebase packages
- Add [FireBase Auth](https://pub.dev/packages/firebase_auth) & [FireBase core](https://pub.dev/packages/firebase_core) packages inside pubspec.yaml file

