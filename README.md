# YFAndroidLibs

## 关于（About）##
这是抽取的工作日常工作代码形成的一个库，持续更新中。借鉴了一些网上现有的代码，在后续的介绍中会逐一提及。本文是基于android的库，后续会有iOS版本以及JS版本
 - 如何抽取
自定义view和布局，然后加以封装，形成aar包。
 - 用法及源码详解见CSDN：http://blog.csdn.net/u011072613/article/details/53889596
 - 欢迎交流，欢迎start。
 
## 功能（Features）
这个库包含的主要内容有：

1. [起始页splash](http://blog.csdn.net/u011072613/article/details/53899141)

2. [第一次导航guidepage](http://blog.csdn.net/u011072613/article/details/53907395)

3. [广告banner](http://blog.csdn.net/u011072613/article/details/53909522)

4. [tab导航和分栏](http://blog.csdn.net/u011072613/article/details/53914988)

5. [定位sqlite数据库](http://blog.csdn.net/u011072613/article/details/53914951)

6. [搜索框和界面](http://blog.csdn.net/u011072613/article/details/53914968)

7. [自定义dialog和Toast](http://blog.csdn.net/u011072613/article/details/53914851)

8. 一些常用的工具类，utils

9. [标签布局TagView](http://blog.csdn.net/u011072613/article/details/53914735)

10. 联动布局LInkageView

其中字体、颜色和背景的样式均可自定义，一键设置。


## 导入（Usage）

   1.导入aar包
  
 - 在libs文件夹下，添加相应的aar包
   
   
 - 在 repositories添加
   
    android {
    compileSdkVersion 24
    buildToolsVersion "24.0.2"

    defaultConfig {
        applicationId "com.yf.memorycard"
        minSdkVersion 14
        targetSdkVersion 24
        versionCode 1
        versionName "1.0"
    }
    buildTypes {
        release {
            minifyEnabled false
            proguardFiles getDefaultProguardFile('proguard-android.txt'), 'proguard-rules.pro'
        }
    }
    repositories {
        flatDir {
            dirs 'libs'
        }
      } 
    }
  
 - 在dependencies 中添加
   
    dependencies {
    compile(name:'yf_Library-release-0.1', ext:'aar')
    }
    
2.maven导入

   还在测试中，敬请期待！
   
2.Jcenter导入

  还在测试中，敬请期待。
  
##代码（Code）
   以SplashVIew为例：
   在布局中添加：

    ` <com.github.yf_library.splash.SplashView
        android:id="@+id/sp_view"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        /> `
        
   在代码中添加逻辑：
       
       //设置闪屏图片
    ` sp_view.setBg(getDrawable(R.drawable.guide1));
	  sp_view.setTime(t,new OnFinishListener() {

			@Override
			public void setFinish() {
				// TODO Auto-generated method stub
				Intent mIntent=new Intent(getApplicationContext(),CommonTestActivity.class);
				startActivity(mIntent);				
			}
		});
        //设置点击跳过
		sp_view.setJumpClick(new OnClickListener() {
			
			@Override
			public void onClick(View v) {
				// TODO Auto-generated method stub
				Toast.makeText(TestActivity.this, "点击跳过", 1).show();;
				Intent mIntent=new Intent(getApplicationContext(),CommonTestActivity.class);
				startActivity(mIntent);			
			}
		});
    `

3.效果图见ScreenShots文件夹

4.其他的还在测试中。敬请期待。

##交流(Contacts)
CSDN:http://blog.csdn.net/u011072613

邮箱：yhcommute@outlook.com
