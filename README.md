# cocosCreator_2.4.6v （windows）
projectBuildProblem

##1##
首先检查java version 是不是 1.8 SE 
打开cmd输入 ：

```
java -version
```
![点击看图片/click here for image](https://user-images.githubusercontent.com/49250073/160803094-05aeacbd-f395-49fb-a241-03313aa2452a.png)
![This is an image](https://myoctocat.com/assets/images/base-octocat.svg)
如果没有的话请去official website download

https://www.oracle.com/java/technologies/downloads/#jdk18-windows

##2##
配置java_environment
[java_environment setup /java环境配置]https://www.runoob.com/w3cnote/windows10-java-setup.html

##3##
下载android studio
跟着这个视频配置Android studio
[Follow Video / 跟随视频]https://www.bilibili.com/video/BV1Z44y1C7t8?spm_id_from=333.1007.top_right_bar_window_history.content.click

##4##
全部好了以后回去打开cocos creator2.4.6v open up cocos creator
去文件-设置-原生开发环境 配置的路径 
ndk ： C:\Users\ccren\AppData\Local\Android\Sdk\ndk\19.2.5345600
sdk ：C:\Users\ahxian\AppData\Local\Android\Sdk

保存

##5##
去project-build project
[click for image/点击查看图像]![image](https://user-images.githubusercontent.com/49250073/160804505-6ca9efa9-9541-43f1-9c9b-f174cbc98c05.png)

然后就构建-编译
如果好了的可以直接去到
C:projectName\build\jsb-default\publish\newProject.apk
过后手机下载运行就可以了 如果没有问题



**问题遇到的 ：**
1.
Error while executing 'projectPath\ndk-build.cmd' with arguments {NDK_PROJECT_PATH=nul ...blablabla}
Go to root build.gradle 不一定解决 请往下看
```
allprojects {
//Adding this buildDir above repositories 
    buildDir = "C:/tmp/${rootProject.name}/${project.name}"
    repositories {
       ...
    }
}
```

如果改了还是不行 出现以下问题 请把buildDir = "c:/tmp/..." delete
[click for image/点击查看图像]![image](https://user-images.githubusercontent.com/49250073/160814167-9b1e98f1-fc84-441c-ad32-bab614bc7bf2.png)

然后把整个cocos proeject 搬运去c drive的 root地方 e.g : **c:/mytestingProject**
不一定全部project都搬运 只有要release(发布)的project才需要放去 root(根)位置

2.
Android studio 打包apk报错Execution failed for task ':app:mergeReleaseResources

aaptOptions.cruncherEnabled = false
aaptOptions.useNewCruncher = false

[click for image/点击查看图像]![image](https://user-images.githubusercontent.com/49250073/160807664-c4bed91d-a902-471b-8674-893eb28b91c1.png)

If required english ver pls email to me **cchunren1997@gmail.com**
