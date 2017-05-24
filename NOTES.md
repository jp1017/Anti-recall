+ [Android Studio自动生成带系统签名的apk](http://www.voidcn.com/blog/cxq234843654/article/p-5996019.html)

+ MainActivity 设置为 singleInstance, 好处:
1. 防止按下home键(先pause, 后resume)重新onCreate, 导致解析两次中心消息

+ `APP` 更新
1. 全量更新, 此时用户会收到弹窗或设置里检查更新
    1. 更新(增大) `versionCode` 和 `versionName`
    1. 上传到 `bugly` 即可
    
1. 增量更新(tinker), 用户无感知, 在同一个基版本上增量, 多个增量, tinkerId可以相同, 只要和基版本不同就可以
    1. `enable' 设置为 `true`
    1. `commit` 一次, 作为 `tinkerId`
    1. 修改 `tinker-support` 中  `baseApkDir`
    1. 上传到 `bugly` 即可


## 一些设置

1. 摄像头个数设置, 只需设置Constants.NUM_UVC_CAMERA即可, 1为单摄像头, 2为双摄像头, 其他错误

音频存放位置:
sd卡无效时： `/storage/emulated/0/Ringtones/`
sd卡正常时： `/storage/sdcard1/Ringtones/`

`DVR` 视频存放位置:
sd卡无效时： `/storage/emulated/0/InstDVR/` 
sd卡正常时： `/storage/sdcard1/InstDVR/`

视频存放位置:
sd卡无效时： `/storage/emulated/0/Movies/`
sd卡正常时： `/storage/sdcard1/Movies/`

图片存放位置:
sd卡无效时： `/storage/emulated/0/Pictures/`
sd卡正常时： `/storage/sdcard1/Pictures/`

## 电源管理

1. 监听模式: `GPIOsManager.getInstance().EnableTrumpetPower(false);`
1. 外放控制: `GPIOsManager.getInstance().EnableAmplifierPower(true);`

## 串口摄像头

1. 下面一个uvc, 对应GPIOsManager.getInstance().EnableCameraPower(true);  拍摄乘客
1. 上面一个uvc, 对应GPIOsManager.getInstance().EnableCamera２Power(true); 行车记录(默认开启)

### 8801指令

1. 摄像头编号, 1--拍摄后置乘客; 2--拍摄前置行车记录

### 视频录制

1. 10分钟视频大小(640 * 480---50M; 320 * 240---17M - 40M)
1. 8G内存卡能持续录制26小时, 大概一天(640); 三天(320)


### 司机刷卡
1. 司机刷卡后从业资格证必须存在且有效(18位数据), 否则不能营运, 加密后存到了 `sp`, 后续根据该资格号查询头像, 二维码及营运数据等
1. 刷卡必须联网, 中心确认无其他签到车辆方可签到成功
1. 刷卡流程见 `司机刷卡流程.png`



### 连续驾驶等报警处理
(以下时间都在钥匙关闭和打开之间)
1. 驾驶时间: 钥匙打开开始计算, 到下一次钥匙关闭(空车状态)结束, 钥匙关闭到打开时间间隔小于最小休息时间
    (可能是重新打火或等红灯等)仍算连续驾驶
1. 停车时间: 钥匙关闭到下一次钥匙打开

### 扬声器打开时机
1. 打开音乐, vlc, 快图浏览时, 此时何时关闭
2. 语音播报时打开, 播报结束关闭
3. 按下音量增减时打开, 3s后关闭

## 权限管理

1. 电话呼入, 电话呼出, 只对司机限制

## 数据库

版本: 1, 对应app版本: 2.11