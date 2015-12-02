---
layout: post
title:  "Developing Android Apps with Facebook's React Native on Linux."
date:   2015-12-02 17:34:28
categories: 
---
[React Native][react-native] is Facebook’s open source framework for building native applications on iOS and Android. It achieves this by providing a common developer experience so that a developer learns one set of tools and can apply it to both platforms (Android and iOS).

Facebook have provided a great documentation and information about React Native on github, however because it’s early days for React Native getting up and running on Linux isn’t as straightforward and easy as it should be. The main reason behind this is Facebook's use OS X for development by its developers , Additionally, It was only availabale for iOS ,the Android version of React Native wasn't been publicly available for very long, so there are fewer resources available.

As of version 0.14 React Native claims its might be supported on Windows and Linux platforms.

So Here is the step by step guide I used to install React Native on `Ubuntu 14.04`.

#Prerequisites :
* Android SDK.
* Node 4.0 or greater. 

#Setup evironment variable that points to current Android SDK directory
{% highlight bash%}
 export ANDROID_HOME=<path_where_you_unpacked_android_sdk>  
 {% endhighlight %}


#Installing React Native node module
{% highlight bash%}
 sudo npm install -g react-native-cli
 {% endhighlight %}


#Creating a New Project
{% highlight bash%}
 react-native init FirstReactNativeApp  
 {% endhighlight %}
This creates a folder named  "FirstReactNativeApp" in your current working directory and installs required node modules and dependencies


#Setting Up ADB
{% highlight bash%}
 export PATH=$PATH{}:<path_where_you_unpacked_android_sdk>/platform-tools  
 {% endhighlight %}
Make sure you have adb defined in environment variables.
	{% highlight bash%}
  adb reverse tcp:8081 tcp:8081  
  {% endhighlight %}
This allows Android to access the Development Server running on PC. 



#Running the Application 
{% highlight bash%}
 cd FirstReactNativeApp  
 react-native run-android  
 {% endhighlight %}
This will build your application and start a development server inside a different terminal.

#It will look something like this.

![My helpful screenshot](http://3.bp.blogspot.com/-BTALTlludWY/Vl4YTg-hE3I/AAAAAAAAFgk/A38UQLvrllY/s1600/Screenshot%2Bfrom%2B2015-11-29%2B00%253A57%253A01.png)

If all goes well, then the application will launch on your device. Shake the phone to open the developer menu and turn on Reload JS. Now, whenever you make changes to the react native source code (such as editing index.android.js), the changes will instantly appear on the device.

#Screenshot of Application

![My helpful screenshot](http://4.bp.blogspot.com/-xhXxgRqt5Kw/Vl4ZJ6ZLe0I/AAAAAAAAFgs/kbnri3rDpqE/s1600/Screenshot_2015-11-29-01-05-33.png)


[react-native]: https://facebook.github.io/react-native/

