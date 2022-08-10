---
title: Environment Build Up of Unreal Engine 4 and MATLAB Co-simulation
top: 1
date: 2022-08-09 15:51:52
tags: 
 - Unreal Engine 4 
 - MATLAB
categories:
 - Tutorial
---

## ***Preface***


This tutorial is divided into two parts:
* <font color='#a83e32'>**Basic Configuration**</font>
* <font color='#5d4587'>**Advanced Configuration**</font>

Among them, <font color='#a83e32'>**Basic Configuration**</font> must be done before the Co-simulation of **MATLAB** and **Unreal Engine** can be performed. And if we have **{% label warning @customization %}** for the **Unreal Engine** environment. Then we need to use the content in <font color='#5d4587'>**Advanced Configuration**</font>.
<!-- more -->

{% note danger %}
**At the front of the two chapters respectively, **{% label warning @the full tutorial video of the chapter %}** will be placed, so we can choose to watch the video or configure according to this article**
{% endnote %}

{% note danger %}
**This tutorial has been successfully tested in MATLAB 2021b and 2022a (at least 2019b or above). If the version is too low, some functions and Simulink blocks may not be supported. If there is a version problem, please upgrade the MATLAB version (or install two versions of MATLAB)**
{% endnote %}

---


## ***Basic Configuration (Required)***


### **<font color='#0047FA'>Video List</font>**
* [**MATLAB and Unreal Engine Co-simulation教學 01：基礎配置**](https://www.youtube.com/watch?v=0i2QfcxRbss){%youtube 0i2QfcxRbss %}

* [**MATLAB and Unreal Engine Co-simulation教學 02：測試環境**](https://www.youtube.com/watch?v=aGFEAEFYBow){%youtube aGFEAEFYBow %}

### <font color='#0047FA'>**STEP.0</font>: Confirm Computer Specifications**
Here we list the **specifications of our computer** and the **recommended specifications for Unreal Engine 4** . If we run Co-simulation later, there is a very long delay and an unexpected crash occurs. It can be inferred that the computer specifications may not meet the minimum requirement which need to be solved through **hardware upgrade** .


|          | Minimum Requirement | Recommended| Ours |
| -------- | -------- | -------- | -------- |
| OS       | Windows 7| Windows 10 64-bit| Windows 10 64-bit|
| CPU      | Intel or AMD four-core CPU, 2.5GHz above| six-core Xeon E5-2643 @3.4GHz| Intel(R) i7-3770 @3.4GHz|
| RAM      | 8GB      | 64GB       |16GB   |
| GPU      | None        | NVIDIA GeForce GTX 970 |NVIDIA GeForce GTX 1660 Ti|
| Disk     | None| 256G SSD (OS Drive)、2TB SSD(Data Drive)|256G SSD(OS Drive)、1TB HDD(Data Drive)| 


{% note danger %}
**It must be confirmed that the Windows user name **{% label warning @cannot be in Chinese %}**, otherwise there may be problems with subsequent software installation and Co-simulation. By the way, if you need to install anything, try to keep it in the **{% label warning @default path %}****
{% endnote %}


### **<font color='#0047FA'>STEP.1</font>: Select the Corresponding MATLAB and Unreal Engine 4 Versions**


* First of all, to determine your own version of MATLAB, you can **directly type the following command** in the commad window
```MATLAB=
version 
```
* Then the output will look like this and we can know  our MATLAB version is R2021b
```MATLAB=
ans =
    '9.11.0.1837725 (R2021b) Update 2'
```

* Go to google search:  [**Unreal Engine Simulation Environment Requirements and Limitations**](https://www.mathworks.com/help/driving/ug/3d-visualization-engine-requirements.html) to find information about **version correspondence** (**MATLAB** and **Unreal Engine**)

{% note success %}
**Unreal Engine 4 and MATLAB version correspondence:**
We can see that the version of Unreal Engine 4 required for MATLAB 2021b is **{% label warning @4.25 %}**
![](https://i.imgur.com/LVOrRWU.png)
{% endnote %}

### **<font color='#0047FA'>STEP.2</font>: Install the Corresponding Version of Unreal Engine 4**
* Go to the **official website of Unreal Engine 4**: [**Unreal Engine official website**](https://www.unrealengine.com/en-US)
* If we don't have an **Epic Game platform account** yet, we must apply for it first. Click **SING IN** in the upper right corner
![](https://i.imgur.com/ea4vMbc.png)

* Choose any registration method
![](https://i.imgur.com/wNiwZlH.png)


{% note primary  %}
**The following omits many registration processes, including mailbox authentication and so on. Just confirm that the login page can be displayed normally which means the registration is successful.**
![](https://i.imgur.com/wCHNmAU.png)
{% endnote %}


* To install Unreal Engine, we must install the **Epic Games launcher** at first. Click **DOWNLOAD** in the upper right corner
![float: right](https://i.imgur.com/wCHNmAU.png)

* Scroll down and click **DOWNLOAD LAUNCHER**
![](https://i.imgur.com/Q7NpBLA.png)

* During installation process, keeps clicking the **next** button.

### **<font color='#0047FA'>STEP.3</font>: Drone Simulation**
#### **Open test example**
* Next we open the following webpage [**Simulate Simple Flight Scenario and Sensor in Unreal Engine Environment**](https://www.mathworks.com/help/uav/ug/simulate-a-simple-flight-scenario-and-sensor-in-3d-environment.html), and press **Copy Command**![](https://i.imgur.com/TMiLn8z.png)
* **Execute the above copied content in MATLAB Command Windows**, it will download and open the folder of the example![](https://i.imgur.com/hGtYBzK.png)
* Click the example **uav_simple_flight_model.slx** file to open the example **Simulink file**
![](https://i.imgur.com/MPM7hc6.png)
* After opening, you will see the **following blocks**. Next, let's **run this block** to make sure that our environment is configured correctly.

{% note danger %}
The default camera module will be fisheye mode. But after many tests, we found that it cannot work properly, **so we must replace it with a normal camera module before running this slx file**.
* First, we go to the Libary Browser to find the camera module in the following path.
**Camera Module Path**: **UAV Toolbox->Simulation 3D->Simulation 3D Camera**
![](https://i.imgur.com/3dhCK72.png)
* **Drag to the main code panel and replace** the original fisheye camera module.
{% endnote %}

* **Press the green run button and we should see something running**. Then we will introduce each block in detail later.


#### **Module Introduction**




### **<font color='#0047FA'>STEP.4</font>: Vehicle Simulation**
**TODO**



### **<font color='#0047FA'>STEP.5</font>: (Multi) Sensor Configuration**
**TODO**

---

## ***Advanced Configuration (Optional, Customized Scene Requirement)***
### **Video List**
---
### **<font color='#0047FA'>STEP.1</font>: Customized Scene (Part I) - Basic Configuration and Modification**
{% note info %}
**If we only want to use MATLAB default scene, the following actions can be omitted**
{% endnote %}

* First enter **MATLAB** and click **Get Add-ones**
![](https://i.imgur.com/rNKFEsR.png)
* Then search for **UAV Toolbox Interface for Unreal Engine Project** and click Install. After the installation is complete, where it was originally **Install** will display **Manage**, as shown below.
![](https://i.imgur.com/AQAZTQ8.png)

{% note warning %}
Do not install to another similar pakage-**Automated Driving Toolbox Interface for Unreal Engine 4 Projects** (This is the Unreal Engine Development Kit for Self-Driving Cars)
![](https://i.imgur.com/7de46sH.png)
{% endnote %}

* First we copy the following code to **MATLAB** and execute it.
```MATLAB=
%%
supportPackageFolder = fullfile( ...
    matlabshared.supportpkg.getSupportPackageRoot, ...
    "toolbox","shared","sim3dprojects","spkg");
localFolder = "C:\Local";
projectFolderName = "AutoVrtlEnv";
projectSupportPackageFolder = fullfile(supportPackageFolder,"project",projectFolderName);
projectLocalFolder = fullfile(localFolder,projectFolderName);
if ~exist(projectLocalFolder,"dir")
    copyfile(projectSupportPackageFolder,projectLocalFolder);
end
ueInstallFolder = "C:\Program Files\Epic Games\UE_4.25";
mwSimPluginName = "MathWorksSimulation.uplugin";
mwSimPluginFolder = fullfile(supportPackageFolder,"plugins","mw_simulation","MathWorksSimulation");
mwUAVPluginName = "MathworksUAVContent.uplugin";
mwUAVPluginFolder = fullfile(supportPackageFolder,"plugins","mw_uav","MathworksUAVContent");

uePluginFolder = fullfile(ueInstallFolder,"Engine","Plugins");
uePluginDestination = fullfile(uePluginFolder,"Marketplace","MathWorks");

cd(uePluginFolder)
foundPlugins = [dir("**/" + mwSimPluginName) dir("**/" + mwUAVPluginName)];

if ~isempty(foundPlugins)
    numPlugins = size(foundPlugins,1);
    msg2 = cell(1,numPlugins);
    pluginCell = struct2cell(foundPlugins);

    msg1 = "Plugin(s) already exist here:" + newline + newline;
    for n = 1:numPlugins
        msg2{n} = "    " + pluginCell{2,n} + newline;
    end
    msg3 = newline + "Please remove plugin folder(s) and try again.";
    msg  = msg1 + msg2 + msg3;
    warning(msg);
else
    copyfile(mwSimPluginFolder, fullfile(uePluginDestination,"MathWorksSimulation"));
    disp("Successfully copied MathWorksSimulation plugin to UE4 engine plugins!")
    copyfile(mwUAVPluginFolder, fullfile(uePluginDestination,"MathworksUAVContent"));
    disp("Successfully copied MathworksUAVContent plugin to UE4 engine plugins!")    
end

```
* The operation content of the above code is mainly divided into two parts:
> * Copy the example **AutoVrtlEnv** (unreal project) that comes with our installation **UAV Toolbox Interface for Unreal Engine Project** to the local folder in C disk (if it doesn't exist, it will be created by itself). Any customized environment will be created based on this project.
{% note info %}
The original path of **AutoVrtlEnv** is: 
<font color="#0060FF">**C:\ProgramData\MATLAB\SupportPackages\R2021b\toolbox\shared\sim3dprojects\spkg\project\AutoVrtlEnv**</font>

{% endnote %}
>* In addition, this is quite important, mainly to install the **plugin** in Unreal Engine that can communicate and control with MATLAB, etc. The installation method is also very intuitive, that is, copy the **plugin** that was originally located in the newly installed package folder and put it in the path where we installed Unreal Engine.
{% note info %}
**{%label warning @The original path of this plugin is (there are two paths)%}**
<font color="#70D100">**C:\ProgramData\MATLAB\SupportPackages\R2021b\toolbox\shared\sim3dprojects\spkg\plugins\mw_simulation\MathWorksSimulation**</font>
<font color="#f00">**C:\ProgramData\MATLAB\SupportPackages\R2021b\toolbox\shared\sim3dprojects\spkg\plugins\mw_uav\MathWorksUAVContent**</font>
**{%label warning @place the above two plugins to the following Unreal Engine path%}**
<font color='#FC00FF'>**C:\Program Files\Epic Games\UE_4.25\Engine\Plugins\Marketplace\MathWorks**</font>
{% endnote %}



### **<font color='#0047FA'>STEP.2</font>: Customized Scene (Part II) - Advanced Configuration and Executable File Generation**
**TODO**
### **<font color='#0047FA'>STEP.3</font>: 【Notice】Customized Scene (Part III) - Import of Real Point Clouds or Maps**
**TODO**
### **<font color='#0047FA'>STEP.4</font>: 【Notice】Customized Scene (Part IV) - Customized Vehicle Appearance**
**TODO**
### **<font color='#0047FA'>STEP.5</font>: 【Notice】Customized Scene (Part V) - Creat a Dynamic Environment**
**TODO**



---

## ***Useful Website***
* Free 3D Model Download: [**FREE 3D**](https://free3d.com/)
![](https://i.imgur.com/f1TgdzZ.png)









---
## ***Reference***
* [**win10配置airsim環境**](https://zhuanlan.zhihu.com/p/267321662)
* [**Unreal Engine官網**](https://www.unrealengine.com/en-US)
* [**How to scan and import real objects to Unreal Engine 4**](https://www.youtube.com/watch?v=Kgwvo4CMlj4)
* [**airsim環境配置教學系列文**](https://www.zhihu.com/column/multiUAV)
* [**Unreal Engine UE4 / Lidar Point Cloud / Leica BLK360 / OSC Plugin Realtime Automation Ipad / Iphone**](https://www.youtube.com/watch?v=3iSCDJrSJQQ)
* [**LiDAR point cloud support | Feature Highlight | Unreal Engine**](https://www.youtube.com/watch?v=R-ZXdAEGbiw)
* [**Install Support Package for Customizing Scenes**](https://www.mathworks.com/help/uav/ug/install-support-package-for-customizing-scenes.html?fbclid=IwAR1XKD-ciqBE500I38WSN4eTwZYp8h5_TIZrr3nzuGhLuOYJgerNbnvrVDQ)
* [**Unreal Engine Scenario Simulation**](https://www.mathworks.com/help/driving/unreal-engine-scenario-simulation.html)