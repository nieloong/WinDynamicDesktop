<!--
 * @Author: nieloong@aliyun.com
 * @Date: 2020-03-09 16:20:41
 * @LastEditors: Loong Nie
 * @LastEditTime: 2020-03-09 23:00:52
 * @FilePath: \WinDynamicDesktop\README.md
 * @Descripttion:
 * @version:
 -->

## 根据时间变换桌面背景软件及主题

- **安装问题**

  > 本人安装时：windows 10 企业版 版本 10240.16520

  1. NET Framework 各版本操作系统支持 > 只支持 net framework 4.6 及以上，不然会报错。

     <font size=1 color=#ff0000>System.IO.FileNotFoundException: 未能加载文件或程序集“netstandard, Version=2.0.0.0, Culture=neutral, PublicKeyToken=cc7b13ffcd2ddd51”或它的某一个依赖项。系统找不到指定的文件。
     文件名:“netstandard, Version=2.0.0.0, Culture=neutral, PublicKeyToken=cc7b13ffcd2ddd51”
     在 WinDynamicDesktop.SunriseSunsetService.GetSolarData(DateTime date)
     在 WinDynamicDesktop.WallpaperChangeScheduler.RunScheduler(Boolean forceImageUpdate)
     在 WinDynamicDesktop.AppContext..ctor(String[] args)
     在 WinDynamicDesktop.Program.Main(String[] args)

     警告: 程序集绑定日志记录被关闭。
     要启用程序集绑定失败日志记录，请将注册表值 [HKLM\Software\Microsoft\Fusion!EnableLog](DWORD)设置为 1。
     注意: 会有一些与程序集绑定失败日志记录关联的性能损失。
     要关闭此功能，请移除注册表值 [HKLM\Software\Microsoft\Fusion!EnableLog]。
     </font>

     _net framework 各版本详细说明_
     [https://blog.csdn.net/nielongwc/article/details/104763173](https://blog.csdn.net/nielongwc/article/details/104763173)


     > **解决方法** 先更新 window 系统，再安装

2. windows 10 系统更新失败问题

   > **解决方法** 老系统各种 Google 解决更新的方法都试验了，最后妥协重装新系统。

3. 主题包命名问题

   > **注意** 避免与默认主题命名区分

4. 主题 JSON 编写

   > 默认情况下，WinDynamicDesktop 使用 Mojave 壁纸，但如果在与 EXE 相同的文件夹中创建 images.conf 文件，则可以自定义使用的图像。这里可以找到默认的 images.conf。它采用 JSON 格式，并且必须包含以下值：
   > [imagesZipUri] - 包含要从中下载 images.zip 文件的 URL 的字符串，如果图像子文件夹中的内容由用户提供，则为 null
   > [imageFilename] - 包含每个壁纸图像文件名的字符串，用{0}代替图像编号
   > [dayImageList] - 列出要在整个一天中（日出与日落之间）显示的图像编号的数字数组
   > [nightImageList] - 列出整个夜晚（日落和日出之间）显示的图像编号的数字列表

   **案例**

   ```JSON {.line-numbers}
   {
    "imagesUrls": "",
    "imageFilename": "mojave_dynamic_*.jpeg", //主题名称+*.jpg
    "imageCredits": "LoongKing", //主题创建者
    "sunriseImageList": [2, 3, 4], //日出图像序号
    "dayImageList": [5, 6, 7, 8, 9, 10, 11], //白天图像序号
    "sunsetImageList": [1, 12, 13], //日落图像序号
    "nightImageList": [14, 15, 16] //夜晚图像序号
   }
   ```

- **主题包**

  > 从文件导入

  ![image](https://github.com/nieloong/WinDynamicDesktop/blob/master/layout/1.png?raw=true)

### 主题文件对应

    **仿 Mac 沙漠** >> f Mojave Desert.zip
    **Earth_View.ddw** >> Earth_View.ddw
    **Firewatch.ddw** >> Firewatch.ddw

- **总结**
  痛并快乐着。。。┑(￣ Д ￣)┍
