# 好好看
### 这个文件夹是安卓嵌入式开发的资源文件夹，里面有期末考试的一些资源，由于老师不提供图片资源，需要自己准备。
## 文件夹的结构
### res 文件夹包含了安卓项目的图片文件，安卓项目的图片资源默认放在res目录下的drawable文件夹中。如果需要适配不同的屏幕密度，可以在drawable文件夹下创建不同的子文件夹，如drawable-hdpi、drawable-xhdpi等，将相应密度的图片放在对应的文件夹中。
格式支持   
PNG格式：支持透明度，无损压缩，适合图标、按钮等小尺寸图片。

JPEG格式：有损压缩，适合照片等大尺寸图片。

GIF格式：支持动画，适合简单的动态图像。

WebP格式：谷歌开发的一种新型图片格式，支持有损和无损压缩，适合网络传输。
### zh.222.202.jar 文件就是安卓汉化包，IDE不是中文就很头疼，适用版本（2022.2.1）
### code 文件夹是保存示例代码的文件夹，实际考试要求需要新建工程使用Main.Activity.xml文件更改代码
### v2RayN 文件夹是proxy代理软件，IDE报错要下载东西需要用到（国内网络环境很几把头疼），里面的节点可能用不了，自求多福吧。
## 示例代码
### 横向布局
您可以使用LinearLayout布局来实现图片横向排布。以下是一个示例代码：
```xml
<LinearLayout
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:orientation="horizontal">

    <ImageView
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_weight="1"
        android:src="@drawable/image1"/>

    <ImageView
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_weight="1"
        android:src="@drawable/image2"/>

    <ImageView
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_weight="1"
        android:src="@drawable/image3"/>

</LinearLayout>
```
在这个示例中，我们使用了一个水平方向的LinearLayout布局，并在其中添加了三个ImageView控件。每个ImageView控件的宽度都被设置为0dp，并且使用了相同的layout_weight属性值，这样它们就会平均分配LinearLayout的宽度，从而实现了横向排布的效果。您可以将@drawable/image1、@drawable/image2和@drawable/image3替换为您自己的图片资源。
### 纵向布局
您可以使用LinearLayout布局来实现图片纵向排布。以下是一个示例代码：
```xml
<LinearLayout
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:orientation="vertical">

    <ImageView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:src="@drawable/image1"/>

    <ImageView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:src="@drawable/image2"/>

    <ImageView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:src="@drawable/image3"/>

</LinearLayout>
```
在这个示例中，我们使用了一个垂直方向的LinearLayout布局，并在其中添加了三个ImageView控件。每个ImageView控件的宽度都被设置为match_parent，这样它们就会占据整个父布局的宽度，从而实现了纵向排布的效果。您可以将@drawable/image1、@drawable/image2和@drawable/image3替换为您自己的图片资源。
## Android studio常见问题
### 镜像更新
使用国内的镜像来下载更新Android Studio。以下是一些常用的国内镜像：

清华大学开源软件镜像站：https://mirrors.tuna.tsinghua.edu.cn/

阿里云开源镜像站：https://developer.aliyun.com/mirror/

中科大开源镜像站：https://mirrors.ustc.edu.cn/

您可以在Android Studio的设置中找到“Appearance & Behavior” -> “System Settings” -> “Updates”，然后在“Channel”下拉菜单中选择“Custom”并在“Update URL”中输入您选择的镜像地址。然后点击“Check Now”按钮来检查更新。