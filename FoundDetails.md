### I will update this file at when i find new things
---
## for remove title bar
```xml
// go to (...)\styles.xml 
<style name="AppTheme" parent="@android:style/Theme.NoTitleBar" />
// detail is -> style/Theme.NoTitleBar
```
---
## customizing objects / drawables
```xml
// create xml file to -> (...) res/drawable/
// file name needs to be lower case
// paste this code =
<?xml version="1.0" encoding="UTF-8"?> 
<shape xmlns:android="http://schemas.android.com/apk/res/android"> 
    <solid android:color="#ffffffff"/>    
</shape>
//usage = android:background="@drawable/ name"
// you can use this pages to learn inner elements =
```
- ##### [Page 1](https://medium.com/android-news/android-shape-drawables-tutorial-17fbece6fef5)
- ##### [Page 2](https://stackoverflow.com/questions/2122199/how-do-i-set-the-rounded-corner-radius-of-a-color-drawable-using-xml)
---
## positioning in relative layout
###### [Directly link](https://developer.android.com/guide/topics/ui/layout/relative)
---
## get battery percent
```java
import android.content.Intent;
import android.content.IntentFilter;
import android.os.BatteryManager;

IntentFilter ifilter = new IntentFilter(Intent.ACTION_BATTERY_CHANGED);
Intent batteryStatus = getApplicationContext().registerReceiver(null, ifilter);
int level = batteryStatus.getIntExtra(BatteryManager.EXTRA_LEVEL, -1);
int scale = batteryStatus.getIntExtra(BatteryManager.EXTRA_SCALE, -1);
float batteryPct = level / (float)scale;
float p =(batteryPct * 100);
```
---
## object get width - height
```java
import android.widget.*;
import android.widget.TextView;
import android.view.View;
import android.view.ViewGroup.LayoutParams;
import android.view.ViewGroup;

final View view1=(View) findViewById(R.id.viewId);
// in this solution, view1 is a guide for view2
view1.post(new Runnable(){
@Override
public void run()
{
 view1.getWidth();
 view1.getHeight();
// using sizes
 View view2=(View) findViewById(R.id.view2);
 ViewGroup.LayoutParams viewG1=view1.getLayoutParams();
 viewG1.width=view1.getWidth()-50;
 view2.setLayoutParams(viewG1);
}
});
```
##### links
#### [link 1](https://stackoverflow.com/questions/3591784/views-getwidth-and-getheight-returns-0)
---
## Android Studio - Adb / Virtual device connection
```cmd
go to this folder (default) -> %localappdata% / android / sdk / platform-tools /
and copy path (for example)-> C:\Users\UserName\AppData\Local\Android\Sdk\platform-tools
open cmd and change directory to that path -> cd "C:\Users\UserName\AppData\Local\Android\Sdk\platform-tools"
and use adb commands , example -> adb connect 127.0.0.1:5555(this is the virtual device's address)
```
---
## Android Studio - Licence fix
```cmd
go to settings / android sdk
change tab SDK Platforms -> SDK Tools
download Google Play Licensing Library 
you can also download Android SDK build Tools
```
### if you cant get string for condition use .equals
```java
String x="Hello World!";
if(x.replace(" ","").equals("HelloWorld!")==true)
{
System.out.println(" HELLO ");
}
```

## Fit UI for all devices
    use Relative Layout Instead Other Layouts

