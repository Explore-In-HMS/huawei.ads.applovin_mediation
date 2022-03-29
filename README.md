 <h1 align="center">Huawei-Applovin Mediation Github Documentation</h3>

![Latest Version](https://img.shields.io/badge/latestVersion-13.4.49.301.2-yellow)
<br>
![Supported Platforms](https://img.shields.io/badge/Supported_Platforms:-Native_Android_-orange)

# Introduction

In this documentation we explained how to use Huawei-Applovin mediation.

# Compatibility

|   | Banner Ad | Interstitial Ad | Rewarded Ad | Native Ad | MREC |
| --- | --- | --- | --- | --- | --- |
| Native (Java/Kotlin) | ✅ | ✅ | ✅ | ✅ |  ✅ |


# How to start?

## Create an ad unit on Huawei Publisher Service

1. Sign in to [Huawei Developer Console](https://developer.huawei.com/consumer/en/console) and create an AdUnit

## Create a mediation network on Applovin

1. Sign in to [Applovin dashboard](https://dash.applovin.com/login)
2. Go to "**Networks -> Click here to add a Custom Network**"
3. Select "**SDK as Network Type**" and give your custom network a name.
4. Enter the class name "**com.applovin.mediation.adapters.HuaweiMediationAdapter**" for Android/FireOS Adapter Class Name.
5. Enter  "**HuaweiMediationAdapter**" for iOS Adapter Class Name
6. Go to "**Ad Units**" tab, and create a new ad unit or modify the existing one.
7. On "**Default Waterfall**" section below the "**Custom Networks & Deals**" enable the Huawei network.
8. Enter the Huawei Ad unit ID  for Placement ID and Enter CPM price for the waterfall. 
   <br>


   **Note:** This [link](https://dash.applovin.com/documentation/mediation/android/mediation-setup/custom-sdk) also can be useful.



<h1 id="integrate-huawei-sdk">
Integrate the Huawei Mediation SDK
</h1>

In the **project-level** build.gradle, include Huawei's Maven repository.

```groovy
repositories {
    maven { url 'https://developer.huawei.com/repo/' } // Add this line
   
}

...

allprojects {
    repositories {
        maven { url 'https://developer.huawei.com/repo/' } //Add this line
        
    }
}
```
<h1 id="app-level">
</h1>
In the app-level build.gradle, include Huawei Ads dependency (required by the adapter) and the adapter

```groovy
dependencies {
    implementation 'com.applovin.mediation:huawei-adapter:13.4.49.301.2'
}
```

[Check the latest version of adapter here](https://mvnrepository.com/artifact/com.applovin.mediation/huawei-adapter) <br>

**Important Note :** Applovin-Huawei adapter released and maintained by Applovin team. Please use [this](https://github.com/AppLovin/AppLovin-MAX-SDK-Android) repository if you have any issues or feedbacks related to Huawei adapter.




## **Permissions**
The HUAWEI Ads SDK (com.huawei.hms:ads) has integrated the required permissions. Therefore, you do not need to apply for these permissions. <br />

**android.permission.ACCESS_NETWORK_STATE:** Checks whether the current network is available.   <br/>

**android.permission.ACCESS_WIFI_STATE:** Obtains the current Wi-Fi connection status and the information about WLAN hotspots. <br />

**android.permission.BLUETOOTH:** Obtains the statuses of paired Bluetooth devices. (The permission can be removed if not necessary.) <br />

**android.permission.CAMERA:** Displays AR ads in the Camera app. (The permission can be removed if not necessary.) <br />

**android.permission.READ_CALENDAR:** Reads calendar events and their subscription statuses. (The permission can be removed if not necessary.) <br />

**android.permission.WRITE_CALENDAR:** Creates a calendar event when a user clicks the subscription button in an ad. (The permission can be removed if not necessary.) <br />

## **Configuring Obfuscation Scripts**
Before building the APK, configure the obfuscation configuration file to prevent the HUAWEI Ads SDK () from being obfuscated.

Open the obfuscation configuration file proguard-rules.pro in the app-level directory of your Android project, and add configurations to exclude the HUAWEI Ads SDK from obfuscation.

```groovy
-keep class com.huawei.openalliance.ad.** { *; }
-keep class com.huawei.hms.ads.** { *; }
```

## **Configuring Network Permissions**
To allow HTTP and HTTPS network requests on devices with targetSdkVersion 28 or later, configure the following information in the AndroidManifest.xml file :

```groovy
<activity
    ...
    android:usesCleartextTraffic="true"
    >
    ...
</activity>
```



# Version Change History

## 13.4.49.301.3

Banner Ad type fixed. 

## 13.4.49.301.2

Banner and MREC adapter classes are added. 

## 13.4.49.301.1

Interstitial,rewarded and native adapter classes are added.



# Platforms

## Native

This section demonstrates how to use Applovin mediation feature with Huawei Ads Kit on Native android app.

Firstly, integrate the Applovin-MAX SDK for Android

[Applovin-MAX Android SDK](https://dash.applovin.com/documentation/mediation/android/getting-started/integration) can be used for all ad types.

**Note** : Developers can find app level build.gradle in their project from __**"app-folder/app/build.gradle"**__

### **Banner Ad**

To use Banner ads in Native android apps, please check the Applovin-MAX SDK. Click [here](https://dash.applovin.com/documentation/mediation/android/getting-started/banners) to get more information about  Applovin-MAX SDKs Banner Ad development.

### **Interstitial Ad**

To use Interstitial ads in Native android apps, please check the Applovin-MAX SDK. Click [here](https://dash.applovin.com/documentation/mediation/android/getting-started/interstitials) to get more information about  Applovin-MAX SDKs Interstitial Ad development.

### **Rewarded Ad**

To use _Rewarded_ ads in Native android _Rewarded_, please check the Applovin-MAX SDK. Click [here](https://dash.applovin.com/documentation/mediation/android/getting-started/rewarded-ads) to get more information about  Applovin-MAX SDKs Rewarded Ad development.

### **Native Ads**

To use _Native_ ads in Native android apps, please check the Applovin-MAX SDK. Click [here](https://dash.applovin.com/documentation/mediation/android/getting-started/native-manual) to get more information about  Applovin-MAX SDKs Native Ad development.

### **MREC Ads**

To use _MREC_ ads in Native android apps, please check the Applovin-MAX SDK. Click [here](https://dash.applovin.com/documentation/mediation/android/getting-started/mrecs) to get more information about  Applovin-MAX SDKs MREC Ad development. <br>

   **Note:** Enter Huawei 300x250 Banner slot ID for Applovin MREC ad type.
 
 <br />
 
 # Screenshots
 <table>
<tr>
<td>
<img src="https://user-images.githubusercontent.com/53767481/160608807-0b0d19a8-02fa-4a45-9325-44d7f2996556.jpg" width="200">

Banner Ad
</td>
 <td>
<img src="https://user-images.githubusercontent.com/53767481/160609711-a9a4841d-1737-4ecd-a66b-68f78f990ae6.jpg" width="200">

Interstitial Ad
</td>

<td>
<img src="https://user-images.githubusercontent.com/53767481/160609047-1b05a4de-2f6e-4246-8339-50d1b887f186.jpg" width="200">

Rewarded Ad
</td>
<td>
<img src="https://user-images.githubusercontent.com/53767481/160609060-b67f5223-352e-4b29-bb48-a8c42b89403f.jpg" width="200">

Native Ad
</td>
</tr>
</tr>
</table>
