每次写项目总是要用到一些通用的组件，决定把这些组件都创建成共享module，用以提高开发速度。

# ToastTools
Android项目中Toast工具，方便全局管理toast（支持显示string，R.string.XXX;可以控制显示位置；可以设置显示成功or失败的图片）

源码如下：

package com.lory.toasttoolsl;

import android.view.Gravity;
import android.view.LayoutInflater;
import android.view.View;
import android.widget.ImageView;
import android.widget.TextView;
import android.widget.Toast;

/**
 * 方法说明：  Toast工具类，全局使用，避免重复弹框，无法立即消除
 * 创建人：lory
 * 创建时间：2019/11/12 10:22
 */
public class ToastUtil {


    private static Toast toast;

    /**
     * 单例模式（防止重复显示）
     */
    private static class ToastHolder {
        private static final Toast toast = new Toast(GlobalUtils.getApplicationContext());
    }

    /**
     * 方法说明：  使用的时候，需要先设置GlobalUtils
     * 创建人：lory
     * 创建时间：2019/11/12 10:26
     */
    public static Toast getInstance() {
        return ToastHolder.toast;
    }

    /**
     * 方法说明： 根据String.xml中的id，获取字串
     * 创建人：lory
     * 创建时间：2019/11/12 10:29
     */
    private static String getToastString(int resName) {
        return GlobalUtils.getApplicationContext().getResources().getString(resName);
    }

    /**
     * 方法说明：  居中显示msg，使用toast系统默认风格
     * 创建人：lory
     * 创建时间：2019/11/12 10:31
     */
    public static void showShortCenter(String msg) {
        if (GlobalUtils.getApplicationContext() == null) {
            return;
        }
        if (toast == null) {
            toast = Toast.makeText(GlobalUtils.getApplicationContext(), msg, Toast.LENGTH_SHORT);
            toast.setGravity(Gravity.CENTER, 0, 0);
            toast.show();
        } else {
            toast.setGravity(Gravity.CENTER, 0, 0);
            toast.setDuration(Toast.LENGTH_SHORT);
            toast.setText(msg);
            toast.show();
        }
    }

    /**
     * 方法说明：  居中显示string.xml中指定name的字串，使用toast系统默认风格
     * 创建人：lory
     * 创建时间：2019/11/12 10:31
     */
    public static void showShortCenter(int resName) {
        if (GlobalUtils.getApplicationContext() == null) {
            return;
        }
        if (toast == null) {
            toast = Toast.makeText(GlobalUtils.getApplicationContext(), getToastString(resName), Toast.LENGTH_SHORT);
            toast.setGravity(Gravity.CENTER, 0, 0);
            toast.show();
        } else {
            toast.setGravity(Gravity.CENTER, 0, 0);
            toast.setDuration(Toast.LENGTH_SHORT);
            toast.setText(getToastString(resName));
            toast.show();
        }
    }


    /**
     * 方法说明：  底部显示msg，使用toast系统默认风格
     * 创建人：lory
     * 创建时间：2019/11/12 10:31
     */
    public static void showShortBottom(String msg) {
        if (GlobalUtils.getApplicationContext() == null) {
            return;
        }
        if (toast == null) {
            toast = Toast.makeText(GlobalUtils.getApplicationContext(), msg, Toast.LENGTH_SHORT);
            toast.setGravity(Gravity.BOTTOM, 0, 0);
            toast.show();
        } else {
            toast.setGravity(Gravity.BOTTOM, 0, 0);
            toast.setDuration(Toast.LENGTH_SHORT);
            toast.setText(msg);
            toast.show();
        }
    }

    /**
     * 方法说明：  底部显示string.xml中指定name的字串，使用toast系统默认风格
     * 创建人：lory
     * 创建时间：2019/11/12 10:31
     */
    public static void showShortBottom(int resName) {
        if (GlobalUtils.getApplicationContext() == null) {
            return;
        }
        if (toast == null) {
            toast = Toast.makeText(GlobalUtils.getApplicationContext(), getToastString(resName), Toast.LENGTH_SHORT);
            toast.setGravity(Gravity.BOTTOM, 0, 0);
            toast.show();
        } else {
            toast.setGravity(Gravity.BOTTOM, 0, 0);
            toast.setDuration(Toast.LENGTH_SHORT);
            toast.setText(getToastString(resName));
            toast.show();
        }
    }

    /**
     * 方法说明：  居中显示msg，使用toast系统默认风格
     * 创建人：lory
     * 创建时间：2019/11/12 10:31
     */
    public static void showLongCenter(String msg) {
        if (GlobalUtils.getApplicationContext() == null) {
            return;
        }
        if (toast == null) {
            toast = Toast.makeText(GlobalUtils.getApplicationContext(), msg, Toast.LENGTH_LONG);
            toast.setGravity(Gravity.CENTER, 0, 0);
            toast.show();
        } else {
            toast.setGravity(Gravity.CENTER, 0, 0);
            toast.setDuration(Toast.LENGTH_LONG);
            toast.setText(msg);
            toast.show();
        }
    }

    /**
     * 方法说明：  居中显示string.xml中指定name的字串，使用toast系统默认风格
     * 创建人：lory
     * 创建时间：2019/11/12 10:31
     */
    public static void showLongCenter(int resName) {
        if (GlobalUtils.getApplicationContext() == null) {
            return;
        }
        if (toast == null) {
            toast = Toast.makeText(GlobalUtils.getApplicationContext(), getToastString(resName), Toast.LENGTH_LONG);
            toast.setGravity(Gravity.CENTER, 0, 0);
            toast.show();
        } else {
            toast.setGravity(Gravity.CENTER, 0, 0);
            toast.setDuration(Toast.LENGTH_LONG);
            toast.setText(getToastString(resName));
            toast.show();
        }
    }


    /**
     * 方法说明：  底部显示msg，使用toast系统默认风格
     * 创建人：lory
     * 创建时间：2019/11/12 10:31
     */
    public static void showLongBottom(String msg) {
        if (GlobalUtils.getApplicationContext() == null) {
            return;
        }
        if (toast == null) {
            toast = Toast.makeText(GlobalUtils.getApplicationContext(), msg, Toast.LENGTH_LONG);
            toast.setGravity(Gravity.BOTTOM, 0, 0);
            toast.show();
        } else {
            toast.setGravity(Gravity.BOTTOM, 0, 0);
            toast.setDuration(Toast.LENGTH_LONG);
            toast.setText(msg);
            toast.show();
        }
    }

    /**
     * 方法说明：  底部显示string.xml中指定name的字串，使用toast系统默认风格
     * 创建人：lory
     * 创建时间：2019/11/12 10:31
     */
    public static void showLongBottom(int resName) {
        if (GlobalUtils.getApplicationContext() == null) {
            return;
        }
        if (toast == null) {
            toast = Toast.makeText(GlobalUtils.getApplicationContext(), getToastString(resName), Toast.LENGTH_LONG);
            toast.setGravity(Gravity.BOTTOM, 0, 0);
            toast.show();
        } else {
            toast.setGravity(Gravity.BOTTOM, 0, 0);
            toast.setDuration(Toast.LENGTH_LONG);
            toast.setText(getToastString(resName));
            toast.show();
        }
    }


    /**
     * 方法说明： 居中显示string.xml中指定name的字串（自定义toast）
     * 创建人：lory
     * 创建时间：2019/11/12 10:56
     */
    public static void showCustomToast(int resName, Boolean isSuccess) {
        if (GlobalUtils.getApplicationContext() == null) {
            return;
        }
        View toastRoot = LayoutInflater.from(GlobalUtils.getApplicationContext()).inflate(R.layout.v_my_toast, null);
        TextView tv_my_toast = toastRoot.findViewById(R.id.tv_my_toast);
        ImageView iv_my_toast = toastRoot.findViewById(R.id.iv_my_toast);
        if (isSuccess) {//成功
            iv_my_toast.setBackgroundResource(R.drawable.icon_toast_success);
        } else {
            iv_my_toast.setBackgroundResource(R.drawable.icon_toast_failure);
        }
        tv_my_toast.setText(GlobalUtils.getApplicationContext().getResources().getString(resName));
        Toast toast = getInstance();
        toast.setGravity(Gravity.CENTER, 0, 0);
        toast.setDuration(Toast.LENGTH_SHORT);
        toast.setView(toastRoot);
        toast.show();
    }


    /**
     * 方法说明： 居中显示text( 自定义toast)
     * 创建人：lory
     * 创建时间：2019/11/12 10:31
     */
    public static void showCustomToast(String text, Boolean isSuccess) {
        if (GlobalUtils.getApplicationContext() == null) {
            return;
        }
        View toastRoot = LayoutInflater.from(GlobalUtils.getApplicationContext()).inflate(R.layout.v_my_toast, null);
        TextView tv_my_toast = toastRoot.findViewById(R.id.tv_my_toast);
        ImageView iv_my_toast = toastRoot.findViewById(R.id.iv_my_toast);
        if (isSuccess) {//成功
            iv_my_toast.setBackgroundResource(R.drawable.icon_toast_success);
        } else {
            iv_my_toast.setBackgroundResource(R.drawable.icon_toast_failure);
        }
        tv_my_toast.setText(text);
        Toast toast = getInstance();
        toast.setGravity(Gravity.CENTER, 0, 0);
        toast.setDuration(Toast.LENGTH_SHORT);
        toast.setView(toastRoot);
        toast.show();
    }

    /**
     * 方法说明： 显示text( 自定义toast)，位置可控制
     * 创建人：lory
     * 创建时间：2019/11/12 10:31
     */
    public static void showCustomToast(String text, Boolean isSuccess, boolean isBottow) {
        if (GlobalUtils.getApplicationContext() == null) {
            return;
        }
        View toastRoot = LayoutInflater.from(GlobalUtils.getApplicationContext()).inflate(R.layout.v_my_toast, null);
        TextView tv_my_toast = toastRoot.findViewById(R.id.tv_my_toast);
        ImageView iv_my_toast = toastRoot.findViewById(R.id.iv_my_toast);
        if (isSuccess) {//成功
            iv_my_toast.setBackgroundResource(R.drawable.icon_toast_success);
        } else {
            iv_my_toast.setBackgroundResource(R.drawable.icon_toast_failure);
        }
        tv_my_toast.setText(text);
        Toast toast = getInstance();
        if (!isBottow) {
            toast.setGravity(Gravity.CENTER, 0, 0);
        } else {
            toast.setGravity(Gravity.BOTTOM, 0, 0);
        }
        toast.setDuration(Toast.LENGTH_SHORT);
        toast.setView(toastRoot);
        toast.show();
    }


    public static void showTopXY(String msg, int X, int Y) {
        if (GlobalUtils.getApplicationContext() == null) {
            return;
        }
        // 如：X= 0; Y=400;
        if (toast == null) {
            toast = Toast.makeText(GlobalUtils.getApplicationContext(), msg, Toast.LENGTH_SHORT);
            toast.setGravity(Gravity.TOP | Gravity.LEFT, X, Y);
            toast.show();
        } else {
            toast.setGravity(Gravity.TOP | Gravity.LEFT, X, Y);
            toast.setText(msg);
            toast.show();
        }
    }


    public static void showMargin(float x, float y, String msg) {
        if (GlobalUtils.getApplicationContext() == null) {
            return;
        }
        if (toast == null) {
            toast = Toast.makeText(GlobalUtils.getApplicationContext(), msg, Toast.LENGTH_SHORT);
            toast.setMargin(x, y);
            toast.show();
        } else {
            toast.setMargin(x, y);
            toast.setText(msg);
            toast.show();
        }
    }
}











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
 
 
 
=============================================================================
============================共享module创建指南===============================
=============================================================================
步骤1：在你要共享的module的build.gradle文件中添加如下语句：

apply plugin: 'maven'

uploadArchives {

    repositories.mavenDeployer {
    
        def mavenDirPath = file('D:\\work\\AwesomeProject2\\Test1112\\ToastToolsL') // 编译好后的共享资源将被存放的目录
        
        repository(url:"file://${mavenDirPath.absolutePath}") // 必须双引号，单引号不会转义$
        
        pom.project {
        
            groupId "com.lory.toasttoolsl" // 可以随意取，一般取包名
            
            artifactId "toasttoolsl" // 可以随意取，一般取库的名字
            
            version "1.0.0" // 版本号
            
        }
    }
}

步骤2：打包生成maven文件
打开Android Studio的命令行，并执行
例如：
D:\work\AwesomeProject2\Test1112>gradlew :toasttoolsl:uploadArchives

其中：D:\work\AwesomeProject2\Test1112是android studio中的Terminal

toasttoolsl 是模块的名字

uploadArchives 是第一步中定义的


步骤3：登录GitHub，右上角点击Your repositories --> New 一个新的

将 D:\\work\\AwesomeProject2\\Test1112\\ToastToolsL 目录下生成的 com直接拖进去上传（com为你指定的groupId "com.lory.toasttoolsl"中的com）


步骤4：生成仓库地址

点击你 项目名称：ToastToolsL ，copy浏览器输入框中的地址

复制出仓库当前界面的链接地址

https://github.com/lx328217976/ToastTools

对其进行修改：

https://raw.githubusercontent.com/Geroff/MavenTest/master

步骤5：将上方使用说明
 
参见文章：
https://blog.csdn.net/fengyulinde/article/details/81392910





