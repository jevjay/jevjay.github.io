---
layout: post
title:  "Installing Unity Hub on Ubuntu 18.04"
date:   2019-11-21 15:41:51 +0100
categories: unity linux
---
I am using Unity on Linux and I **love** it. I know, I know this might sound controversial but hear me out...

I have used Unity on every single platform: Windows, Mac and now Linux. For both Windows & Mac versions, I had no complaints, as both had their advantages and shortcomings, yet the overall experience was "smooth" and enjoyable. Linux was the whole other story...

My first try at using Unity on Ubuntu a couple of years ago ended up in a fiasco... The installation/configuration process was close to "a nightmare", with countless hours spent online searching for an answer for different issues. Since then I swore to never touch this version of Unity ever again and moved on... Until now...

A month ago I have decided to try out one more time installing Unity on my Ubuntu 18.04 and oh my god I was taken by a surprise. The installation process was easy, all that's required is the outmost basic knowledge of Terminal usage. You simply go to [this](https://forum.unity.com/threads/unity-hub-v2-0-0-release.677485/) and download the latest version of Unity Hub.

After the file was downloaded, head out to the Terminal and execute the following commands:

{% highlight shell %}
cd ~/Downloads
chmod +x UnityHub.AppImage  
./UnityHub.AppImage
{% endhighlight %}

That's it and as always, I hope you found this read useful.
