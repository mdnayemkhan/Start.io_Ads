# Start.io_Ads
Set up start.io ad network in your android project

>Step 1. Add the JitPack repository to your app-level build.gradle file
```
repositories {
  mavenCentral()
}
```
>Step 2.Add the ependencie build.gradle file with correct version:
```
dependencies {
  implementation 'com.startapp:inapp-sdk:4.10.+'
}
```

>Step 3.Updating Your AndroidManifest.xml File
```
<uses-permission android:name="android.permission.BLUETOOTH" />
<uses-permission android:name="android.permission.Ad_ID" />
<uses-permission android:name="android.permission.INTERNET" />  
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />  
```

>Step 4.Add following meta-data tag under the <application> section in your manifest file:
```
<meta-data android:name="com.startapp.sdk.APPLICATION_ID" 
android:value="startapp_app_id" />
```
  
  >Step 5.The Splash Ad is enabled by default. If you want to disable:
```
StartAppAd.disableSplash()
```
  >Step 6.If want to show test ad,use it when app run on your phone:
```
StartAppSDK.setTestAdsEnabled(true);
```
  
  >Step 7.Show Interstitial Ads on Button click:
```
button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                Intent second =new Intent(MainActivity.this,SecondActivity.class);
                startActivity(second);
                StartAppAd.showAd(MainActivity.this);
            }
        });
```
  >Step 8.if you want to show Interstitial Ads when click back:
```
@Override
public void onBackPressed() {
    StartAppAd.onBackPressed(this);
    super.onBackPressed();
}
```
  
  >Step 9.Add the following View inside your Activity layout XML for Banner Ads:
```
<com.startapp.sdk.ads.banner.Banner 
 android:id="@+id/startAppBanner" 
 android:layout_width="wrap_content" 
 android:layout_height="wrap_content" 
 android:layout_centerHorizontal="true" />
```
  
  >Step 10.Your Activity layout XML For 1200X628 px Cover ads:
```
<com.startapp.sdk.ads.banner.Cover 
android:id="@+id/startAppCover" 
android:layout_width="wrap_content" 
android:layout_height="wrap_content" 
android:layout_centerHorizontal="true" />
```
  
  
