# Android-Studio-Gradle-Script
Gradle Script 
plugins {
    id 'com.android.application'
}

android {
    namespace 'com.example.riadtravelapp'
    compileSdk 33

    defaultConfig {
        applicationId "com.example.riadtravelapp"
        minSdk 23
        targetSdk 33
        versionCode 1
        versionName "1.0"

        testInstrumentationRunner "androidx.test.runner.AndroidJUnitRunner"
    }

    buildTypes {
        release {
            minifyEnabled false
            proguardFiles getDefaultProguardFile('proguard-android-optimize.txt'), 'proguard-rules.pro'
        }
    }

    compileOptions {
        sourceCompatibility JavaVersion.VERSION_1_8
        targetCompatibility JavaVersion.VERSION_1_8
    }
}

dependencies {

    // Core UI libraries (compatible with API 33)
    implementation 'androidx.appcompat:appcompat:1.6.1'
    implementation 'com.google.android.material:material:1.9.0'

    // FIXED: compatible ConstraintLayout (IMPORTANT)
    implementation 'androidx.constraintlayout:constraintlayout:2.1.4'

    // Navigation (safe versions for API 33)
    implementation 'androidx.navigation:navigation-fragment:2.5.3'
    implementation 'androidx.navigation:navigation-ui:2.5.3'

    // Profile installer FIX (downgraded automatically safe version)
    implementation 'androidx.profileinstaller:profileinstaller:1.3.1'

    // Testing
    testImplementation 'junit:junit:4.13.2'
    androidTestImplementation 'androidx.test.ext:junit:1.1.5'
    androidTestImplementation 'androidx.test.espresso:espresso-core:3.5.1'
}
