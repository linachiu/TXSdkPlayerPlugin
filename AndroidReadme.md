
# Android SDK

1. 加入gradle 
* compile 'com.android.support:appcompat-v7:25.+'
* compile 'com.android.support:recyclerview-v7:25.+'
* compile 'com.squareup.okhttp3:logging-interceptor:3.8.1'
* compile 'com.github.ctiao:DanmakuFlameMaster:0.5.3'
* compile 'com.android.support:multidex:1.0.0'
* compile 'com.android.support.constraint:constraint-layout:1.0.2'
    
2. 加入ＴＸＳＤＫ
* compile(name: 'LiteAVSDK_Professional', ext: 'aar')

3. 砍掉一些檔案＆資料夾
* common.activity.videopreview/TCVideoPreviewActivity
* txsdk.common.misc/RoomListViewAdapter
* push/LivePublisherActivity (import videoupload)
* push/LivePublisherActivity
(import com.example.advmedia.txsdk.common.activity.videopreview.TCVideoPreviewActivity;
Intent intent = new Intent(getApplicationContext(), TCVideoPreviewActivity.class);)
