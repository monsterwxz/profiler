# profiler

## 描述
这是一个主要用于逆向工程师用来跟踪java方法调用流程的工具。Android Studio本来也具有这个功能，但是过于臃肿，且不适合于逆向工程是操作。因此我将其从AS之中剥离出来，且重写了界面，参考了jadx的界面。

## 使用之前必读

### 背景
使用之前你必须了解，Trace Java Method功能本来是Android系统用来调试应用程序的。当我们需要追踪记录一个进程的java方法，该进程必须得开启jdwp线程，否则无法进行接下来的操作。换言之，该进程/app必须是处于debuggable状态下。

### 如何开启debuggable
目前有两种方式开启debuggable，一种是修改apk的manifest文件，加入debuggable标志，另一种是修改Android的全局prop，其中修改全局prop，网上有各种方法，其中重新编译debuggable版本的系统比较稳定。确保进程开启了debuggable便可以愉快的操作啦。

## 使用
使用shell命令可以直接开启profiler，第一次开启需要在dialog之中填入adb的路径，然后链接上设备就可以愉快的使用啦。
```shell
java -jar profiler.jar
```

该工具也可以直接查看.trace文件。

![](https://github.com/chason0528/profiler/blob/master/screenshoot/main.png)
