# GoogleAdMobAndroid
<h2>How to add Google Adsense Ads to your Android App</h2>
<b>The following is a step by step guide for us to integrate Google AdSense Ads to android application.</b>

Login to Google Adsense site for google ads.

<a href="https://www.google.com/adsense">https://www.google.com/adsense</a>

After that select AdMob option from menu

Go to AdMob and sign in to <a href="https://www.google.com/admob/">AdMob </a>

Click on <strong>Add App</strong> button and Enter application name, select android platform and click on <strong>ADD</strong> button.

First we are adding <strong>banner ads</strong> so we select banner, Enter <strong>Ad unit name</strong> and select Ad type from <strong>Advanced settings</strong> After that click on <strong>CREATE AD UNIT</strong>

After creating AD UNIT follow the below instructions for add Ads using app ID:

Open <strong>project-level build.gradle</strong> and add <strong>maven</strong> directive and click on <strong>sync now </strong>
<pre>maven {
    url "https://maven.google.com"
}</pre>

Open <strong>app-level build.gradle</strong> and add latest <strong>google ads</strong> dependency for added Mobile Ads SDK and select <strong>Sync</strong> button
<pre>compile 'com.google.android.gms:play-services-ads:11.6.0'</pre>

Adding Mobile Ads SDK by calling <strong>MobileAds.initialize()</strong> with saved <strong>AdMob App ID</strong>
<pre>MobileAds.initialize(this, "YOUR_ADMOB_APP_ID");
</pre>
<h3><strong>Implement a Banner</strong></h3>

add <strong>AdView</strong> in<strong> xml</strong> file for banner ads.

    <com.google.android.gms.ads.AdView 
          xmlns:ads="http://schemas.android.com/apk/res-auto"
          android:id="@+id/adView"
          android:layout_width="match_parent"
          android:layout_height="wrap_content"
          android:layout_alignParentBottom="true"
          android:layout_centerHorizontal="true"
          ads:adSize="BANNER"
          ads:adUnitId="ca-app-pub-7643266345625929/3537614550" />


<ul>
 	<li><span style="color: #800000;"><strong>Ads: AdSize</strong></span> - Set ad size - <a href="https://developers.google.com/admob/android/banner?hl=en-GB#banner_sizes">banner size section</a></li>
 	<li><span style="color: #800000;"><strong>Ads: AdUnitId</strong></span>  - Set saved unique identifier from <a href="https://support.google.com/admob/answer/7356431?hl=en-GB">ad unit</a> in your app where ads are to be displayed.</li>
</ul>
<strong>banner sizes</strong>
<table>
<tbody>
<tr>
<th>Size in dp (WxH)</th>
<th>Description</th>
<th>Availability</th>
<th>AdSize constant</th>
</tr>
<tr>
<td>320x50</td>
<td>Standard Banner</td>
<td>Phones and Tablets</td>
<td><code>BANNER</code></td>
</tr>
<tr>
<td>320x100</td>
<td>Large Banner</td>
<td>Phones and Tablets</td>
<td><code>LARGE_BANNER</code></td>
</tr>
<tr>
<td>300x250</td>
<td>IAB Medium Rectangle</td>
<td>Phones and Tablets</td>
<td><code>MEDIUM_RECTANGLE</code></td>
</tr>
<tr>
<td>468x60</td>
<td>IAB Full-Size Banner</td>
<td>Tablets</td>
<td><code>FULL_BANNER</code></td>
</tr>
<tr>
<td>728x90</td>
<td>IAB Leaderboard</td>
<td>Tablets</td>
<td><code>LEADERBOARD</code></td>
</tr>
<tr>
<td><i>Screen width</i> x 32|50|90</td>
<td>Smart Banner</td>
<td>Phones and Tablets</td>
<td><code>SMART_BANNER</code></td>
</tr>
</tbody>
</table>
<h3 id="load_an_ad">Load an ad</h3>
<pre>AdView mAdView = findViewById(R.id.adView);
AdRequest adRequest = new AdRequest.Builder().build();
mAdView.loadAd(adRequest);

</pre>
Add above code in activity.

[Read More...](http://tutorialstack.in/integrating-google-ads-in-android)
