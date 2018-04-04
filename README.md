# android-gradle-dependency
Android gradle depedency in one place

# How to use

add in app gradle
```
apply from:'https://raw.githubusercontent.com/BambangHeriSetiawan/android-gradle-dependency/master/depedency.gradle
```

implement in dependency
```
dependencies {
    implementation fileTree(dir: 'libs', include: ['*.jar'])
    
    /* Android Support */
    implementation libraries.appcompatV7
    implementation libraries.supportV4
    implementation libraries.design
    implementation libraries.constraintLayout
    
    /* RxAndroid, RxJava, Okhttp, okhttp interceptor, Retrofir 2, GSON, rxAdapter */
    implementation libraries.rxandroid
    implementation libraries.rxjava2
    implementation libraries.okhttp
    implementation libraries.interceptor
    implementation libraries.gson
    implementation libraries.retrofit2
    implementation libraries.adapterRxjava2
    implementation libraries.converterGson
    implementation libraries.retrofit2Rxjava2Adapter

    /* Dagger 2 */
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

# Versioning control

# How to use

add in app gradle

enable version control 

make sure your project git project


```
apply from:'https://raw.githubusercontent.com/BambangHeriSetiawan/android-gradle-dependency/master/depedency.gradle
```
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
