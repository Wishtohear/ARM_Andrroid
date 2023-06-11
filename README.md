# 好好看
### 这个文件夹是安卓嵌入式开发的资源文件夹，里面有期末考试的一些资源，由于老师不提供图片资源，需要自己准备。
## 文件夹的结构
### res 文件夹包含了安卓项目的图片文件，安卓项目的图片资源默认放在res目录下的drawable文件夹中。如果需要适配不同的屏幕密度，可以在drawable文件夹下创建不同的子文件夹，如drawable-hdpi、drawable-xhdpi等，将相应密度的图片放在对应的文件夹中。
格式支持   
PNG格式：支持透明度，无损压缩，适合图标、按钮等小尺寸图片。

JPEG格式：有损压缩，适合照片等大尺寸图片。

GIF格式：支持动画，适合简单的动态图像。

WebP格式：谷歌开发的一种新型图片格式，支持有损和无损压缩，适合网络传输。

注意：文件名称不能有特殊字符，最好纯英文名字。
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
### 表格布局

使用表格布局实现的登陆界面，包含一个用户名输入框、一个密码输入框和一个登陆按钮。其中，用户名输入框和密码输入框都使用了权重属性，使它们在表格中占据相同的宽度。登陆按钮使用了布局重心属性，使它在表格中水平居中。在Java代码中，我们可以通过findViewById()方法获取到布局文件中的控件，并为登陆按钮设置点击事件。
在这个示例中，我们使用了一个垂直方向的LinearLayout布局，并在其中添加了三个ImageView控件。每个ImageView控件的宽度都被设置为match_parent，这样它们就会占据整个父布局的宽度，从而实现了纵向排布的效果。您可以将@drawable/image1、@drawable/image2和@drawable/image3替换为您自己的图片资源。
```xml
<TableLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:padding="16dp">

    <TableRow>
        <TextView
            android:text="用户名："
            android:textSize="16sp"
            android:paddingRight="8dp" />
        <EditText
            android:id="@+id/username_edittext"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:inputType="text" />
    </TableRow>

    <TableRow>
        <TextView
            android:text="密码："
            android:textSize="16sp"
            android:paddingRight="8dp" />
        <EditText
            android:id="@+id/password_edittext"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:inputType="textPassword" />
    </TableRow>

    <TableRow>
        <Button
            android:id="@+id/login_button"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="登陆"
            android:layout_gravity="center_horizontal" />
    </TableRow>

</TableLayout>
```
### 5张图片滚动播放
这是一个使用ViewPager控件实现的图片滚动播放界面，包含5张图片。在布局文件中，我们只需要添加一个ViewPager控件即可。在Java代码中，我们创建了一个ImagePagerAdapter类来为ViewPager控件提供数据。在instantiateItem()方法中，我们创建了一个ImageView控件，并为它设置了图片资源和缩放类型，然后将它添加到ViewPager控件中。在destroyItem()方法中，我们将ImageView控件从ViewPager控件中移除。最后，在onCreate()方法中，我们将ImagePagerAdapter类设置为ViewPager控件的适配器。

```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <androidx.viewpager.widget.ViewPager
        android:id="@+id/view_pager"
        android:layout_width="match_parent"
        android:layout_height="match_parent" />

</RelativeLayout>
```
这段代码用到了以下安卓类：

AppCompatActivity：一个支持应用程序向后兼容的Activity基类。

ViewPager：一个支持滑动切换页面的控件。

PagerAdapter：一个抽象类，用于为ViewPager控件提供数据。

ImageView：一个用于显示图片的控件。

ViewGroup：一个抽象类，用于管理子控件的布局。

要在Java文件的开头添加以下import语句来导入这些类：
```java
import androidx.appcompat.app.AppCompatActivity;
import androidx.viewpager.widget.ViewPager;
import android.view.View;
import android.view.ViewGroup;
import android.widget.ImageView;
import androidx.viewpager.widget.PagerAdapter;
```

```java
public class MainActivity extends AppCompatActivity {

    private ViewPager mViewPager;
    private int[] mImageIds = 
    {
        R.drawable.image1, 
        R.drawable.image2, 
        R.drawable.image3, 
        R.drawable.image4, 
        R.drawable.image5
    };

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        mViewPager = findViewById(R.id.view_pager);
        mViewPager.setAdapter(new ImagePagerAdapter());
    }

    private class ImagePagerAdapter extends PagerAdapter {

        @Override
        public int getCount() {
            return mImageIds.length;
        }

        @Override
        public boolean isViewFromObject(View view, Object object) {
            return view == object;
        }

        @Override
        public Object instantiateItem(ViewGroup container, int position) {
            ImageView imageView = new ImageView(MainActivity.this);
            imageView.setImageResource(mImageIds[position]);
            imageView.setScaleType(ImageView.ScaleType.CENTER_CROP);
            container.addView(imageView);
            return imageView;
        }

        @Override
        public void destroyItem(ViewGroup container, int position, Object object) {
            container.removeView((ImageView) object);
        }
    }
}
```
### Scroll View滚动视图
水平滚动

在这个例子中，我们使用了HorizontalScrollView来包含一个LinearLayout，LinearLayout中包含了多个ImageView控件，每个ImageView控件显示一张图片。当用户在屏幕上水平滑动时，HorizontalScrollView会自动滚动，从而实现水平滚动的效果。
```xml
<HorizontalScrollView
    android:layout_width="match_parent"
    android:layout_height="wrap_content">

    <LinearLayout
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:orientation="horizontal">

        <ImageView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:src="@drawable/image1"/>

        <ImageView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:src="@drawable/image2"/>

        <ImageView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:src="@drawable/image3"/>

        <ImageView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:src="@drawable/image4"/>

        <ImageView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:src="@drawable/image5"/>

    </LinearLayout>
</HorizontalScrollView>
```
垂直滚动

在这个例子中，我们使用了ScrollView来包含一个LinearLayout，LinearLayout中包含了多个ImageView控件，每个ImageView控件显示一张图片。当用户在屏幕上垂直滑动时，ScrollView会自动滚动，从而实现垂直滚动图片的效果。注意，这里的图片资源需要在drawable文件夹中提前准备好。
```xml
<ScrollView
    android:layout_width="match_parent"
    android:layout_height="match_parent">

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

        <ImageView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:src="@drawable/image4"/>

        <ImageView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:src="@drawable/image5"/>

    </LinearLayout>
</ScrollView>

```
### Grid View网格视图
可以使用GridView来实现网格图片排列的安卓程序，并且需要编写一个适配器来将数据绑定到GridView上。以下是一个简单的例子：
```xml
<GridView
    android:id="@+id/grid_view"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:numColumns="3"
    android:verticalSpacing="10dp"
    android:horizontalSpacing="10dp"
    android:padding="10dp"/>
```
```java
import android.content.Context;
import android.os.Bundle;
import android.view.View;
import android.view.ViewGroup;
import android.widget.BaseAdapter;
import android.widget.GridView;
import android.widget.ImageView;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    private GridView mGridView;
    private ImageAdapter mAdapter;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        mGridView = findViewById(R.id.grid_view);
        mAdapter = new ImageAdapter(this);
        mGridView.setAdapter(mAdapter);
    }

    private class ImageAdapter extends BaseAdapter {

        private Context mContext;
        private int[] mImageIds = {
            R.drawable.image1,
            R.drawable.image2,
            R.drawable.image3, 
            R.drawable.image4, 
            R.drawable.image5
            };

        public ImageAdapter(Context context) {
            mContext = context;
        }

        @Override
        public int getCount() {
            return mImageIds.length;
        }

        @Override
        public Object getItem(int position) {
            return null;
        }

        @Override
        public long getItemId(int position) {
            return 0;
        }

        @Override
        public View getView(int position, View convertView, ViewGroup parent) {
            ImageView imageView;
            if (convertView == null) {
                imageView = new ImageView(mContext);
                imageView.setLayoutParams(new GridView.LayoutParams(ViewGroup.LayoutParams.MATCH_PARENT, 300));
                imageView.setScaleType(ImageView.ScaleType.CENTER_CROP);
            } else {
                imageView = (ImageView) convertView;
            }

            imageView.setImageResource(mImageIds[position]);
            return imageView;
        }
    }
}
```
### Gallery画廊视图
我们需要创建一个名为CircularImageAdapter的Java类，继承自BaseAdapter。我们将使用Gallery控件并设置适配器的监听事件，以便在手指移到图片上方时放大突出显示该图片。

首先，创建一个名为CircularImageAdapter的Java类：
```java
import android.content.Context;
import android.view.View;
import android.view.ViewGroup;
import android.widget.BaseAdapter;
import android.widget.Gallery;
import android.widget.ImageView;

public class CircularImageAdapter extends BaseAdapter {
    private Context mContext;
    private int[] mImageIds;

    public CircularImageAdapter(Context context, int[] imageIds) {
        mContext = context;
        mImageIds = imageIds;
    }

    @Override
    public int getCount() {
        return Integer.MAX_VALUE;
    }

    @Override
    public Object getItem(int position) {
        return mImageIds[position % mImageIds.length];
    }

    @Override
    public long getItemId(int position) {
        return position;
    }

    @Override
    public View getView(int position, View convertView, ViewGroup parent) {
        ImageView imageView;
        if (convertView == null) {
            imageView = new ImageView(mContext);
            imageView.setLayoutParams(new Gallery.LayoutParams(200, 200));
            imageView.setScaleType(ImageView.ScaleType.FIT_XY);
        } else {
            imageView = (ImageView) convertView;
        }

        imageView.setImageResource(mImageIds[position % mImageIds.length]);
        return imageView;
    }
}

```
接下来，在您的Activity中设置Gallery控件，并为其设置适配器和监听器：
```java
import android.app.Activity;
import android.os.Bundle;
import android.view.View;
import android.widget.AdapterView;
import android.widget.AdapterView.OnItemClickListener;
import android.widget.AdapterView.OnItemSelectedListener;
import android.widget.Gallery;

public class GalleryActivity extends Activity {
    private Gallery mGallery;
    private int[] mImageIds = {R.drawable.image1, R.drawable.image2, R.drawable.image3};

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_gallery);

        mGallery = (Gallery) findViewById(R.id.gallery);
        CircularImageAdapter adapter = new CircularImageAdapter(this, mImageIds);
        mGallery.setAdapter(adapter);

        mGallery.setOnItemSelectedListener(new OnItemSelectedListener() {
            @Override
            public void onItemSelected(AdapterView<?> parent, View view, int position, long id) {
                ImageView imageView = (ImageView) view;
                imageView.setLayoutParams(new Gallery.LayoutParams(300, 300));
            }

            @Override
            public void onNothingSelected(AdapterView<?> parent) {
            }
        });

        mGallery.setOnItemClickListener(new OnItemClickListener() {
            @Override
            public void onItemClick(AdapterView<?> parent, View view, int position, long id) {
                // Handle item click event here
            }
        });
    }
}

```
在布局文件中，添加一个Gallery控件：
```xml
<Gallery
        android:id="@+id/gallery"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true" />
```
### TabHost视图

## Android studio常见问题
### 镜像更新
使用国内的镜像来下载更新Android Studio。以下是一些常用的国内镜像：

清华大学开源软件镜像站：https://mirrors.tuna.tsinghua.edu.cn/

阿里云开源镜像站：https://developer.aliyun.com/mirror/

中科大开源镜像站：https://mirrors.ustc.edu.cn/

您可以在Android Studio的设置中找到“Appearance & Behavior” -> “System Settings” -> “Updates”，然后在“Channel”下拉菜单中选择“Custom”并在“Update URL”中输入您选择的镜像地址。然后点击“Check Now”按钮来检查更新。