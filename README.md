# TXSdkPlayerPlugin
add Tencent player SDK into Unity

1. 取其中資料夾 Player,Third, common, app, Resource, Assets.xcassets ,push(推播)

2. 匯入 TXLiteAV_professional.framework （選加入group）

3. 匯入他說的一堆 framework

4. 看target參數

5. target -> Build Setting -> preprocessor Macros 

  增加tag   ENABLE_PLAY 或是有的沒的

6. 加入common, third, Player, app 資料夾（ 選加入group ）

7. Build Setting -> Search path -> head search Paths 需要設定

	原專案這邊是空的 可是這裡好像繼承了unity的設定  所以要看一下怎麼設定

	https://blog.csdn.net/u012703795/article/details/24464837

8. 砍掉一些檔案＆資料夾
```
檔案
CustomProcessFilter.m
superPlayer/ListUI/LiVIdeoCell.m
superPlayer/ZFPlayer.h. --//#import <Masonry/Masonry.h>

資料夾
common/BeautySettingPanel/ZipArchive/ZipArchive.mm
common/VideoCompress
common/VideoLoading
common/VideoLoadingController
third/QBImagePicker
third/Masonry
player/superplayer

資源資料夾
rescorce/videoedit/裡面的bundel 
```

9. Build Setting -> exception

10. 匯入framework  
	* Accelerate framework
	* sqliteb3, 
	* MobileCoreServices.framework 
	* SystemConfiguration.framework

11. 加入麥克風權限
    加入相機權限
