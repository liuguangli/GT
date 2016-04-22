1.本Andorid工程主体源码是GT Console的源码。

2.本工程依赖于5个jar:   
    (1)android-support-v13.jar   
    (2)mid-sdk-2.xx.jar，请到mta.qq.com网站下载   
    (3)mta-sdk-2.x.x.jar，请到mta.qq.com网站下载   
    (4)zxing.jar，请到https://github.com/zxing/zxing下载   
    (5)wlogin_sdk.jar，暂未开源，仅用于qq帐号登录，请暂时移除相关代码   
请编译前将上述jar包放到工程根路径下的libs目录中。   

如使用抓包功能，需将tcpdump下载至工程根目录下的/res/raw/目录中。对应各Android系统版本的tcpdump可以通过自行编译Android系统的获取，在工具集中找到二进制可执行文件。

3.具体模块描述请参考src目录中各package中的package-info.java文件。

4.根目录下的sdk目录，是GT SDK的源码及其调试的壳工程。需要将GT SDK导出jar包时，请选中src目录，及在eclipse中即时生成的gen目录中的package:com.tencent.wstt.gt及其子package导出jar即可。

5.根目录下的demo目录，是合入了GT SDK的一个被测app样例工程，可以直接用eclipse导入。

-----

**没有修改任何代码，依赖 jar 可自行根据下面方法获取**

### 依赖jar来源说明
* android-support-v13.jar  sdk/extras/android/support/v13/android-support-v13.jar
* mid-sdk-xx.jar,mta-sdk-xx.jar,bugly_crash_release__xx.jar 到腾讯官网下载
* zxing-core-3.2.1.jar  http://central.maven.org/maven2/com/google/zxing/core/
* wlogin_sdk.jar  使用的是GT_2.2.6.2.apk 中反编译出的 jar.

>
打包wlogin_sdk.jar方法   
1. 提取 GT_2.2.6.2.apk 中的 dex 转为 jar   
2. `jar -xf classes-dex2jar.jar`  
3. `rm -rf android/ com/ mqq/`  
4. `jar -cvf wlogin_sdk.jar oicq/`  
         
>res/raw/tcpdump 和 res/raw/tcpdump6 解压自GT_2.2.6.2.apk
 
### Gradle Build
1. 修改local.properties 为本地 sdk,ndk 目录
2. 修改build.gradle 中的签名

`gradle build` 编译即可。
