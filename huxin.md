###Android 各个工具的使用
* ddms 调试监视服务
* hierarchyviewer 查看树形结构 手机设备需要root权限
* uiautomatorviewer  UI层级界面分析
* adb  Android 调试桥
* monkey 稳定性工具
* monkeyrunner  Android 自动化测试工具

###adb 各个命令
* adb deivces 查看手机设备号
* adb install (包名).apk 示例 ：adb install C:\Users\Administrator\Desktop\phoneNurse.apk 安装APK
* adb uninstall cn.goalwisdom.nurseapp  卸载APK
* adb shell pm list package 查看当前设备所有的pakage
* adb logcat | grep ActivityManager  打印日志，筛选出含ActivityManager的信息
* adb push /users/local/xxxx.txt   /sdcard/xxxx.txt 从电脑目录中传文件到手机目录中
* adb pull  从手机目录传文件到电脑目录
* adb shell 进如手机shell 命令
* adb shell wm size  查看设备的分辨率

###Monkey三种不同策略的脚本，并阐述策略
* adb shell monkey -p com.tencent.mm -v -v -v  2000 D:\text.txt 微信执行monkey测试,随机点击2000次，将执行结果保存到D盘根目录下text文件中
* adb shell monkey -p com.tencent.mm.ui.LauncherUI -v -v -v  2000 D:\text1.txt
微信执行ui.LauncherUI 的Activity 随机点击，将结果保存到text1文件中
* adb shell monkey -p —ignore-timeouts -v -v -v -p com.tencent.mm —throttle 5000 1000 打印最详细的日志，每个动作之间等待5秒，点击1000次
* adb shell monkey  -v -v -v -p  com.tencent.mm --ignore-timeouts  --throttle 1000 1000  在运行monkey时出现错误也会执行monkey测试，运行100次每次延迟1秒 打印最详细的日志信息


>Monkey:这个命令太过单调了，尝试查看官方文档之后，多使用参数组合来试试看

###安装ideviceinstaller, 下载一个任意open source的xcode project 在simulator上面运行
