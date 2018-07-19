
# Android SDK

1. 加入gradle 
* compile 'com.android.support:appcompat-v7:25.+'
* compile 'com.android.support:recyclerview-v7:25.+'
* compile 'com.squareup.okhttp3:logging-interceptor:3.8.1'
* compile 'com.github.ctiao:DanmakuFlameMaster:0.5.3'
* compile 'com.android.support:multidex:1.0.0'
* compile 'com.android.support.constraint:constraint-layout:1.0.2'

1.1 加入aar
* 全體gradle 加入
```
allprojects {
    repositories {
        jcenter()
        flatDir {
            dirs 'libs'
        }
    }
}
```
* module 加入
```
dependencies {
    compile fileTree(dir: 'libs', include: ['*.jar'])
    compile fileTree(dir: 'src/main/jniLibs', includes: ['*.jar'])

    androidTestCompile('com.android.support.test.espresso:espresso-core:2.2.2', {
        exclude group: 'com.android.support', module: 'support-annotations'
    })

    compile(name: 'zxing-1.8.4', ext: 'aar')
    compile(name: 'barcodescanner-core-1.8.4', ext: 'aar')
    compile(name: 'volley-1.0.0', ext: 'aar')
    compile(name: 'LiteAVSDK_Professional_4.7.4395', ext: 'aar')
    compile(name: 'liteimsdk-release', ext: 'aar')
    compile files('libs/unity-classes.jar')


    compile 'com.android.support:appcompat-v7:25.+'
    compile 'com.android.support:recyclerview-v7:25.+'
    compile 'com.android.support:multidex:1.0.0'

    compile 'com.android.support.constraint:constraint-layout:1.0.2'
    compile 'com.squareup.okhttp3:logging-interceptor:3.8.1'
    compile 'com.github.ctiao:DanmakuFlameMaster:0.5.3'
    testCompile 'junit:junit:4.12'
}
```


2. 加入ＴＸＳＤＫ
* compile(name: 'LiteAVSDK_Professional', ext: 'aar')

3. 砍掉一些檔案＆資料夾
* common.activity.videopreview/TCVideoPreviewActivity
* txsdk.common.misc/RoomListViewAdapter
* push/LivePublisherActivity (import videoupload)
* push/LivePublisherActivity
(import com.example.advmedia.txsdk.common.activity.videopreview.TCVideoPreviewActivity;
Intent intent = new Intent(getApplicationContext(), TCVideoPreviewActivity.class);)
* play/LivePlayerActivity
(import com.example.advmedia.txsdk.common.activity.videopreview.TCVideoPreviewActivity;
Intent intent = new Intent(getApplicationContext(), TCVideoPreviewActivity.class);)
* play/NewVodPlayerActivity
* play.wkvideoplayer.view/SuperVideoPlayer


3. Unity plugin/Android/資料夾下放入ＳＤＫ.aar

4. 在使用的時候發生了 ``` Android.view.InflateException: Binary XML file line ```
所以在 ``` AndroidManifest ```加上 ``` android:largeHeap="true" ```
