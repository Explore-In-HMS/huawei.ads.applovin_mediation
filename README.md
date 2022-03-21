 <h1 align="center">Huawei-Applovin Mediation Github Documentation</h3>

![Latest Version](https://img.shields.io/badge/latestVersion-13.4.49.301.2-yellow)
<br>
![Supported Platforms](https://img.shields.io/badge/Supported_Platforms:-Native_Android_-orange)
# Introduction

In this documentation we explained how to use Huawei-Applovin mediation.

# Compatibility

|   | Banner Ad | Interstitial Ad | Rewarded Ad | Native Ad | MREC |
| --- | --- | --- | --- | --- | --- |
| Native (Java/Kotlin) | ❌ | ✅ | ✅ | ✅ |  ✅ |


# How to start?

## Create an ad unit on Huawei Publisher Service

1. Sign in to [Huawei Developer Console](https://developer.huawei.com/consumer/en/console) and create an AdUnit

## Create a custom mediation on Applovin

1. Sign in to [Applovin console](https://dash.applovin.com/login)
2. Go to "**Networks -> Click here to add a Custom Network**"
3. Select "**SDK as Network Type**" and give your custom network a name.
4. Enter the class name "**com.applovin.mediation.adapters.HuaweiMediationAdapter**" as Android/FireOS Class Name, and your Huawei's AdUnit ID from step 1 as the parameter
5. Add the adapter and its dependencies into your project



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

[Check the latest version of adapter here](#version-change-history)



**Important:** _To add Huawei Ads Kit SDK and Mediation adapter, the native project should be opened with Android Studio._

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
To allow HTTP and HTTPS network requests on devices with targetSdkVersion 28 or later, configure the following information in the AndroidManifest.xml file:

```groovy
<application
    ...
    android:usesCleartextTraffic="true"
    >
    ...
</application>
```



# Version Change History

## 1.2.7

Logs issue fixed.

## 1.2.4

AdListener methods has been added.

## 1.2.3

OnLoaded() methods has been added .

## 1.2.2

Ads version updated and Zip Path Traversal issue is fixed.

## 1.2.1

Min SDK updated.

## 1.2.0

Transparency & Consent Framework v2.0 and personalized & non-personalized ads configurations are integrated.

# Platforms

## Native

This section demonstrates how to use AdMob mediation feature with Huawei Ads Kit on Native android app.

Make sure to check the article on [How to use Huawei Ads with AdMob mediation (Native Android)](https://medium.com/huawei-developers/how-to-use-huawei-ads-with-admob-mediation-native-android-8fc41438dfad)

Firstly, integrate the Admob SDK for Android

[Admob Android SDK](https://developers.google.com/admob/android/quick-start) can be used for all ad types.

**Note** : Developers can find app level build.gradle in their project from __**"app-folder/app/build.gradle"**__

### **Banner Ad**

To use _Banner_ ads in Native android apps, please check the Admob SDK. Click [here](https://developers.google.com/admob/android/banner) to get more information about Admob SDKs _Banner_ Ad development.

### **Interstitial Ad**

To use Interstitial ads in Native android apps, please check the Admob SDK. Click [here](https://developers.google.com/admob/android/interstitial-fullscreen) to get more information about Admob SDKs Interstitial Ad development.

### **Rewarded Ad**

To use _Rewarded_ ads in Native android _Rewarded_, please check the Admob SDK. Click [here](https://developers.google.com/admob/android/rewarded-fullscreen) to get more information about Admob SDKs _Banner_ Ad development.

### **Native Ads**

To use _Native_ ads in Native android apps, please check the Admob SDK. Click [here](https://developers.google.com/admob/android/native/start) to get more information about Admob SDKs _Native_ Ad development.

## **Unity**

This section demonstrates how to use Admob mediation feature with Huawei Ads Kit on Unity.

Make sure to check the article on [How to use Huawei Ads with Supported Ad Platforms in Unity ?](https://medium.com/huawei-developers/how-to-use-huawei-ads-with-supported-ad-platforms-in-unity-2be08c943a7f)

**Supported Ad Formats are:** Banner Ads, Interstitial Ads and Rewarded Ads.

Firstly, integrate the Admob Unity SDK to Unity.

For more details on Admob Unity SDK visit [here](https://developers.google.com/admob/unity/quick-start)

### **Banner Ads**
To use Banner ads in Unity , please check the Admob Unity SDK. Click [here](https://developers.google.com/admob/unity/banner) to get more information about Admob Unity SDKs Banner Ad development.

### **Interstitial Ads**
To use Interstitial ads in Unity, please check the Admob Unity SDK. Click [here](https://developers.google.com/admob/unity/interstitial) to get more information about Admob Unity SDKs Interstitial Ad development.

### **Rewarded Ads**
To use Rewarded ads in Unity, please check the Admob Unity SDK. Click [here](https://developers.google.com/admob/unity/rewarded) to get more information about Admob Unity SDKs Banner Ad development.

#### **Step 1:**
Make sure to switch to the Android Platform from **Build Settings -> Android -> Switch Platform**
#### **Step 2:**
**Edit -> Project Settings ->  Player -> Other Settings**<br>
In Other Settings set minimum API level to at least **21**.
#### **Step 3:**
**Edit -> Project Settings ->  Player -> Publishing Settings**<br>
In Publishing Settings select **“Custom Main Gradle Template”** , **“Custom Base Gradle Template”** and **“Custom Greadle Properties Template”** <br>
This will let you override **mainTemplate.gradle** , **baseProjectTemplate.gradle** and **gradleTemplate.properties** files in the project.
#### **Step 4:**
**baseProjectTemplate.gradle** is equal to **project-level gradle** so you have to include **Huawei's Maven repositories** from the Integrate the Huawei Mediation SDK section from [**here**](#integrate-huawei-sdk) <br>
**mainTemplate.gradle** is equal to **app-level build.gradle** so you have to include **dependencies** from the Integrate the Huawei Mediation SDK section from [**here**](#app-level).
#### **Step 5:**
Open **gradleTemplate.properties** and add the following lines
```groovy
android.useAndroidX=true
android.enableJetifier=true
```

**After these configurations is completed you can display Huawei Ads.**

**Note:**
In case of any error on aaptOptions you can add the following line to aaptOptions in **launcherTemplate.gradle** which you override it by enabiling it from **Edit -> Project Settings ->  Player -> Publishing Settings**

```groovy
aaptOptions {
        noCompress = ['.ress', '.resource', '.obb'] + unityStreamingAssets.tokenize(', ')
        ignoreAssetsPattern = "!.svn:!.git:!.ds_store:!*.scc:.*:!CVS:!thumbs.db:!picasa.ini:!*~"
    }
```

## React Native

This section demonstrates how to use AdMob mediation feature with Huawei Ads Kit on React-Native.

Make sure to check the article on [How to use Huawei Ads with AdMob mediation (React Native)](https://medium.com/huawei-developers/how-to-use-huawei-ads-with-admob-mediation-react-native-e02a78ebb1eb)

**Important:** _There is no official React Native SDK for Admob therefore third party SDKs has been used in the demonstration._

Firstly, integrate the React Native Admob SDKs as below depending on type of ad

**Note**: Developers can find app level build.gradle in their project from __**"app-folder/app/build.gradle"**__

For **Banner** , **Interstitial** and **Rewarded** Ad type's [react-native-admob](https://github.com/sbugert/react-native-admob) SDK can be used.

For **Native** ad type [react-native-admob-native-ads](https://github.com/ammarahm-ed/react-native-admob-native-ads) SDK can be used.

Then use the following sample codes based on specific ad types.

## **Sample Codes Based on Ad Types**

### **Banner Ad**

```jsx
<AdMobBanner
adSize="fullBanner"
adUnitId={BannerAdId}
testDevices={[AdMobBanner.simulatorId]}
onAdFailedToLoad={error => console.error(error)} />
```

### **Interstitial Ad**

```jsx
AdMobInterstitial.setAdUnitID(InterstitialAdId);
AdMobInterstitial.setTestDevices([AdMobInterstitial.simulatorId]);
AdMobInterstitial.requestAd().then(() => AdMobInterstitial.showAd());
```

### **Rewarded Ad**

```jsx
AdMobRewarded.setAdUnitId(RewardedAdId);
AdMobRewarded.requestAd().then(() => AdMobRewarded.showAd());
```
### **Native Ads**

```jsx
<NativeAdView
adUnitID= {NativeAdId} 
onAdFailedToLoad={error => console.error(error)} /> 
```

## Flutter

This section demonstrates how to use AdMob mediation feature with Huawei Ads Kit on Flutter.

Make sure to check the article on [How to use Huawei Ads with AdMob mediation (Flutter)](https://medium.com/huawei-developers/how-to-use-huawei-ads-with-admob-mediation-flutter-8a3fc3bb1793)

**Important:** _There is no official Flutter SDK for_ AdMob _therefore third party SDKs has been used in the demonstration._

Firstly, integrate the Flutter_ AdMob _SDKs as below depending on type of ad

**Note**: Developers can find app level build.gradle in their project from  __**"app-folder/android/app/build.gradle"**__

For **Banner** and **Interstitial** Ad types [admob\_flutter](https://github.com/kmcgill88/admob_flutter) SDK can be used.

For **Banner** and **Rewarded** Ad types [googleads-mobile-flutter](https://github.com/googleads/googleads-mobile-flutter) SDK can be used.

### **Native Ad**

Native ads are not supported with this SDK. To use Native ads in Flutter app, please check the HMS Core Ads Kit Flutter SDK. Click [here](https://developer.huawei.com/consumer/en/doc/development/HMS-Plugin-Guides-V1/native-ads-0000001050198817-V1) to get more information about HMS Core Flutter SDKs Native Ad development.

Then use the following sample codes based on specific ad types.


## **Sample Codes Based on Ad Types**

### **Banner Ad**

```dart
…
Admob.initialize();
…
child: AdmobBanner(
  adUnitId: "Your Banner Ad Unit ID",
  adSize: AdMobBannerSize.[Selected_Banner_Size],
  listener: (AdmobAdEvent event,
      Map<String, dynamic> args) {
    handleEvent(event, args, 'Banner');
  },
  onBannerCreated:
      (AdmobBannerController controller) {
  },
),
…
```
### **Interstitial Ad**

```dart
…
Admob.initialize();
…
interstitialAd = AdmobInterstitial(
  adUnitId: "Your Intersitatial Ad Unit ID",
  listener: (AdmobAdEvent event, Map<String, dynamic> args) {
    if (event == AdmobAdEvent.closed) interstitialAd.load();
    handleEvent(event, args, 'Interstitial');
  },
);
```
### **Rewarded Ad**

```dart
class RewardedAd extends AdWithoutView {
  ...
  static final String testAdUnitId = Platform.isAndroid
      ? 'Your Rewarded Ad Unit ID'
      : 'Your Rewarded Ad Unit ID';

  @override
  Future<void> load() async {
    await instanceManager.loadRewardedAd(this);
  }
}
```

## Cordova

This section demonstrates how to use AdMob mediation feature with Huawei Ads Kit on Cordova.

Make sure to check the article on [How to use Huawei Ads with AdMob mediation (Cordova)](https://medium.com/huawei-developers/how-to-use-huawei-ads-with-admob-mediation-cordova-f48986f40ab1)

**Important:** _There is no official Cordova SDK for_ AdMob _therefore third party SDKs has been used in the demonstration._

Firstly, integrate the Cordova_ AdMob _SDKs as below depending on type of ad

**Note**: Developers can find app level build.gradle in their project from __**"app-folder/platforms/android/app/build.gradle"**__

For **Banner** and **Interstitial** Ad types [admob-plus](https://github.com/admob-plus/admob-plus) SDK can be used.

### **Rewarded Ad**

Rewarded ads are not supported with this SDK. To use Rewarded ads in Cordova app, please check the HMS Core Ads Kit Cordova SDK. Click [here](https://developer.huawei.com/consumer/en/doc/development/HMS-Plugin-Guides-V1/rewarded-ads-0000001050195456-V1) to get more information about HMS Core Cordova SDKs Rewarded Ad development.

### **Native Ad**

Native ads are not supported in Cordova. To use Native Ads in Cordova App please check the HMS Core Ads Kit Cordova SDK. Click [here](https://developer.huawei.com/consumer/en/doc/development/HMS-Plugin-Guides-V1/native-ads-0000001050197495-V1) to get more information about HMS Core Cordova SDK Native Ad development.

Then use the following sample codes based on specific ad types.

## **Sample Codes Based on Ad Types**

### **Banner Ads**
```js
showBannerAd() {
  const banner = new admob.BannerAd({
    adUnitId: '[Enter BannerAdID here]',
  })
  return banner.show({ position: 'bottom' })
},
```

### **Interstitial Ads**

```js
showInterstitialAd() {
  const interstitial = new admob.InterstitialAd({
          adUnitId: '[Enter InterstitialAdID here]',
  })
  return interstitial.load().then(() => interstitial.show())
},
```

# Screenshots

## AdMob
<table>
<tr>
<td>
<img src="https://user-images.githubusercontent.com/41696219/109941743-8626a780-7ce4-11eb-8aa8-4da1e3f1092f.png" width="200">

Banner Ad
</td>

<td>
<img src="https://user-images.githubusercontent.com/41696219/109941887-aa828400-7ce4-11eb-9409-d93adf506724.JPG" width="200">

Interstitial Ad
</td>

<td>
<img src="https://user-images.githubusercontent.com/41696219/109941974-c4bc6200-7ce4-11eb-81b8-e35a2589d528.JPG" width="200">

Rewarded Ad
</td>
<td>
<img src="https://user-images.githubusercontent.com/41696219/109942031-d43bab00-7ce4-11eb-815f-403918a6b7f4.png" width="200">

Native Ad
</td>
</tr>
</tr>
</table>

## Huawei
<table>
<tr>
<td>
<img src="https://user-images.githubusercontent.com/41696219/109942123-ee758900-7ce4-11eb-96a3-11cce5454c51.png" width="200">

Banner Ad
</td>

<td>
<img src="https://user-images.githubusercontent.com/41696219/109939330-01d32500-7ce2-11eb-9e39-6a9237ca8c54.JPG" width="200">


Interstitial Ad
</td>

<td>
<img src="https://user-images.githubusercontent.com/41696219/109942227-0baa5780-7ce5-11eb-8b69-086924473db0.png" width="200">

Rewarded Ad
</td>
<td>
<img src="https://user-images.githubusercontent.com/41696219/109942307-211f8180-7ce5-11eb-8c3e-7d21903bf6d1.png" width="200">

Native Ad
</td>

</tr>
</tr>
</table>




