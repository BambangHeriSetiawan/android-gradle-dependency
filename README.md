# android-gradle-dependency
Android gradle depedency in one place

#How to use

add in app gradle
```
apply from:'https://raw.githubusercontent.com/BambangHeriSetiawan/android-gradle-dependency/master/depedency.gradle
```

implement in devepency
```
implementation libraries.appcompatV7
```

#Versioning control

#How to use

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
