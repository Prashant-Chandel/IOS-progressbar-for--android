# IOS-progressbar-for--android
IOS type progress bar for android

# DEMO Screen shots



![alt text](https://github.com/Prashant-Chandel/IOS-progressbar-for--android/blob/master/Screenshot/Screenshot_1556862103.png)
![alt text](https://github.com/Prashant-Chandel/IOS-progressbar-for--android/blob/master/Screenshot/Screenshot_1556862107.png)
![alt text](https://github.com/Prashant-Chandel/IOS-progressbar-for--android/blob/master/Screenshot/Screenshot_1556862110.png)
![alt text](https://github.com/Prashant-Chandel/IOS-progressbar-for--android/blob/master/Screenshot/Screenshot_1556862113.png)
![alt text](https://github.com/Prashant-Chandel/IOS-progressbar-for--android/blob/master/Screenshot/Screenshot_1556862128.png)
![alt text](https://github.com/Prashant-Chandel/IOS-progressbar-for--android/blob/master/Screenshot/Screenshot_1556862338.png)
![alt text](https://github.com/Prashant-Chandel/IOS-progressbar-for--android/blob/master/Screenshot/Screenshot_1556862348.png)
![alt text](https://github.com/Prashant-Chandel/IOS-progressbar-for--android/blob/master/Screenshot/Screenshot_1556862355.png)
![alt text](https://github.com/Prashant-Chandel/IOS-progressbar-for--android/blob/master/Screenshot/Screenshot_1556862358.png)
![alt text](https://github.com/Prashant-Chandel/IOS-progressbar-for--android/blob/master/Screenshot/Screenshot_1556862361.png)
![alt text](https://github.com/Prashant-Chandel/IOS-progressbar-for--android/blob/master/Screenshot/Screenshot_1556862373.png)



# Adding IOSProgressHUD to your project


step 1:Add it in your root build.gradle at the end of repositories:

	allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
Step 2. Add the dependency

	dependencies {
	        implementation 'com.github.Prashant-Chandel:Videoplayer-with-Vimeo-support:138257e15c'
	}
            
# For Maven dependency use 

<repositories>
		<repository>
		    <id>jitpack.io</id>
		    <url>https://jitpack.io</url>
		</repository>
	</repositories>
  
Step 2. Add the dependency

	<dependency>
	    <groupId>com.github.Prashant-Chandel</groupId>
	    <artifactId>Videoplayer-with-Vimeo-support</artifactId>
	    <version>138257e15c</version>
	</dependency>            
            
  
  # Code Implementation
  
# Compatibility
Android 4.4 and later

Gradle
Include this in your app build.gradle

# Usage
For a working implementation of this project see the sample app.The usage of IOSProgressHUD is pretty straight forward.

Create the HUD, customize its style and show on the UI thread.
Fire a background worker to handle long-running tasks.
When done, call dismiss() to close (or if you use a determinate style, the HUD will automatically dismiss when progress reaches its max).

# Indeterminate HUD
```java
IOSProgressHUD.create(MainActivity.this)
	.setStyle(IOSProgressHUD.Style.SPIN_INDETERMINATE)
	.setLabel("Please wait")
	.setDetailsLabel("Downloading data")
	.setCancellable(true)
	.setAnimationSpeed(2)
	.setDimAmount(0.5f)
	.show();
 ```
# Determinate HUD
```java
IOSProgressHUD hud = IOSProgressHUD.create(MainActivity.this)
					.setStyle(KProgressHUD.Style.ANNULAR_DETERMINATE)
					.setLabel("Please wait")
					.setMaxProgress(100)
					.show();
hud.setProgress(90);
```
You can also create a custom view to be displayed.

```java
ImageView imageView = new ImageView(this);
imageView.setBackgroundResource(R.drawable.spin_animation);
AnimationDrawable drawable = (AnimationDrawable) imageView.getBackground();
drawable.start();
IOSProgressHUD.create(MainActivity.this)
   .setCustomView(imageView)
   .setLabel("This is a custom view")
   .show();
 ```  
Optionally, the custom view can implement Determinate or Indeterminate interface, which make the HUD treats this view like the default determinate or indeterminate one.

See Javadocs or sample for more information.

# License

Copyright 2019  Prashant chandel <chandela.prashant14@gmail.com>

                    GNU GENERAL PUBLIC LICENSE
                       Version 3, 29 June 2007
 Everyone is permitted to copy and distribute verbatim copies
 of this license document, but changing it is not allowed.

                            Preamble

  The GNU General Public License is a free, copyleft license for
software and other kinds of works.

  The licenses for most software and other practical works are designed
to take away your freedom to share and change the works.  By contrast,
the GNU General Public License is intended to guarantee your freedom to
share and change all versions of a program--to make sure it remains free
software for all its users.  We, the Free Software Foundation, use the
GNU General Public License for most of our software; it applies also to
any other work released this way by its authors.  You can apply it to
your programs, too.

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

