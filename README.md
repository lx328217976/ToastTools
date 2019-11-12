# ToastTools
Android  Toast  工具Module

第一步：
在项目的总build.gradle中添加

maven {
            url "https://raw.githubusercontent.com/lx328217976/ToastTools/master"
        }
        
例如：
allprojects {

    repositories {
    
        google()
        
        jcenter()
        
        maven {
            url "https://raw.githubusercontent.com/lx328217976/ToastTools/master"
        }
    }

}

第二步：
在你的application中的onCreate()初始化 GlobalUtils

例如：
GlobalUtils.setApplicationContext(this);

第三步：
你就可以在项目中随时调用ToastUtil的方法了

例如：
 ToastUtil.showCustomToast("我的第一个共享module",true);

