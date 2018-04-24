# android-gradle-dependency
Android gradle depedency in one place

#How to use

add in app gradle
```
apply from:'https://raw.githubusercontent.com/BambangHeriSetiawan/android-gradle-dependency/master/depedency.gradle
```

implement in devepency
```
dependencies {
    implementation fileTree(dir: 'libs', include: ['*.jar'])
    /*Android Supprot*/
    implementation libraries.appcompatV7
    implementation libraries.supportV4
    implementation libraries.design
    implementation libraries.constraintLayout
    /*RxAndroid, RxJava, Okhttp, okhttp interceptor, Retrofir 2, GSON, rxAdapter*/
    implementation libraries.rxandroid
    implementation libraries.rxjava2
    implementation libraries.okhttp
    implementation libraries.interceptor
    implementation libraries.gson
    implementation libraries.retrofit2
    implementation libraries.adapterRxjava2
    implementation libraries.converterGson
    implementation libraries.retrofit2Rxjava2Adapter

    /*Dagger 2*/
    annotationProcessor libraries.dagger2Compiler
    annotationProcessor libraries.dagger2Processor
    implementation libraries.dagger
    implementation libraries.daggerAndorid
    implementation libraries.daggerAndroidSupport

    testImplementation 'junit:junit:4.12'
    androidTestImplementation 'com.android.support.test:runner:1.0.1'
    androidTestImplementation 'com.android.support.test.espresso:espresso-core:3.0.1'
}
```

#Versioning control

#How to use

add in app gradle

enable version control 

make sure your project git project


```
https://raw.githubusercontent.com/BambangHeriSetiawan/android-gradle-dependency/master/git-version.gradle
```
defaultConfig {
        
        versionCode gitVersionCode
        versionName gitVersionName
        ...
    }
```
```
git tag v1.0
git push --all
```

run in terminal android studio
```
./gradlew printVersion
```
output 
```
Version Name: v1.0
Version Code: 1
Version Code Time: 1522818316
```
# Sample use custom_gradle.gradle

```
apply plugin: 'com.android.library'
apply plugin: 'kotlin-android'
apply plugin: 'kotlin-kapt'
apply plugin: 'kotlin-android-extensions'

android {
    compileSdkVersion versions.compileSdk
    buildToolsVersion versions.buildTools

    defaultConfig {
        minSdkVersion versions.minSdk
        targetSdkVersion versions.compileSdk
        versionCode 1
        versionName "1.0"

        testInstrumentationRunner "android.support.test.runner.AndroidJUnitRunner"

    }

    buildTypes {
        release {
            postprocessing {
                removeUnusedCode false
                removeUnusedResources false
                obfuscate false
                optimizeCode false
                proguardFile 'proguard-rules.pro'
            }
            buildConfigField 'String', 'BASE_URL', '"http://jsonplaceholder.typicode.com/"'
        }
        debug {
            buildConfigField 'String', 'BASE_URL', '"http://jsonplaceholder.typicode.com/"'
        }
    }

    compileOptions {
        sourceCompatibility versions.sourceCompat
        targetCompatibility versions.targetCompat
    }
}

dependencies {
    api fileTree(include: ['*.jar'], dir: 'libs')
    api deps.support.appCompat
    api deps.support.recyclerView
    api deps.support.cardView
    api deps.support.support
    api deps.support.designSupport

    api deps.android.lifecycleExt
    api deps.android.lifecycleCommon
    api deps.android.roomRuntime
    api deps.android.roomRx

    api deps.kotlin.stdlib

    api deps.reactivex.rxJava
    api deps.reactivex.rxAndroid

    api deps.google.dagger
    kapt deps.google.daggerProcessor
    api deps.google.gson

    api deps.square.picasso
    api deps.square.okhttpDownloader

    api deps.square.retrofit
    api deps.square.okhttp
    api deps.square.gsonConverter
    api deps.square.retrofitRxAdapter

    implementation deps.facebook.stetho
    implementation deps.facebook.networkInterceptor
}

```
