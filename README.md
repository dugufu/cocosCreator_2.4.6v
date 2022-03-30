# cocosCreator_2.4.6v （windows）
projectBuildProblem

##1##
首先检查java version 是不是 1.8 SE 
打开cmd输入 ：

```
java -version
```
![image](https://user-images.githubusercontent.com/49250073/160803094-05aeacbd-f395-49fb-a241-03313aa2452a.png)

如果没有的话请去official website download

https://www.oracle.com/java/technologies/downloads/#jdk18-windows

##2##
配置java_environment
https://www.runoob.com/w3cnote/windows10-java-setup.html

##3##
下载android studio
跟着这个视频配置Android studio
https://www.bilibili.com/video/BV1Z44y1C7t8?spm_id_from=333.1007.top_right_bar_window_history.content.click

##4##
全部好了以后回去cocos creator2.4.6v
去文件-设置-原生开发环境 配置的路径 
ndk ： C:\Users\ccren\AppData\Local\Android\Sdk\ndk\19.2.5345600
sdk ：C:\Users\ahxian\AppData\Local\Android\Sdk

保存

##5##
去project-build project
![image](https://user-images.githubusercontent.com/49250073/160804505-6ca9efa9-9541-43f1-9c9b-f174cbc98c05.png)

然后就构建-编译
如果好了的可以直接去到
C:projectName\build\jsb-default\publish\newProject.apk

过后手机下载运行就可以了

问题遇到的 ：
Error while executing 'projectPath\ndk-build.cmd' with arguments {NDK_PROJECT_PATH=nul ...blablabla}
Go to root build.gradle
```
allprojects {
//Adding this buildDir above repositories 
    buildDir = "C:/tmp/${rootProject.name}/${project.name}"
    repositories {
       ...
    }
}
```
