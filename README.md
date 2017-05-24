# 防撤回神器
<h2 align="center">--免Root查看撤回消息!</h2>
<hr>

# 导入 `AS`, 可直接编译运行!!! 

### 引言

#### 安卓市场上防撤回软件五花八门, 但全都是需要root的, 不仅麻烦, 随之而来的安全问题令人担忧. 那么, 能不能不要root呢?

#### 当然啦, 下面我就给大家带来我用课余时间开发了半年之久的**防撤回神器**!

<hr>

### 废话不多说, 先看效果展示:

#### 撤回文字消息:

  <img src=https://github.com/JasonQS/Anti-recall/blob/master/demo/demo01.gif width=300px>
<br>

#### 撤回图片消息:

  <img src=https://github.com/JasonQS/Anti-recall/blob/master/demo/demo02.gif width=300px>
<br>
<hr>

### 软件使用方法
要注意的地方软件里边我都有写, 这边简单写两句:

* 首先打开辅助功能里的开关

   * 找不到的朋友可以

   * 从我的软件里

   * 点击右上角的菜单

   * 进入辅助功能的设置

* 然后!为了检查手机的辅助功能是否正常开启

   * 打开QQ或者微信

   * 应该会收到一条表示成功的弹窗

   * 如图 
   <img src=https://github.com/JasonQS/Anti-recall/blob/master/demo/notification.jpg width=200px>

 
* **[重要]**如果没有的话需要**重启**哦

* 为了帮助理解软件的运作
  * 在菜单里有一个**调试模式**的开关
  
  * 开启之后所有被收录的消息都会以顶部弹窗的方式显示出来
  
  * 同时会生成日志
  
  * 如果报issue请带上日志哦

<hr>

### 软件 十大 技术点 !

##### (详细可以看源码, 我注释写的挺清楚了)
            
1. 撤回消息需要点击才会显示, 交互方式**很舒服!**

2. 监听微信QQ通知栏, 不遗漏任何一条消息 (好吧其实通知栏的更容易截获)

3. 通过一层层解析UI而不是根据控件的ID获取屏幕上的聊天信息,**解决了微信控件的ID会随升级而改变的问题!**

4. 把聊天记录存入本地, 有需要的时候查找, 如何正确的找到撤回的消息也是本程序一大**难点!**</p>

5. **[4.0新增]** 更复杂, 更完善的查找算法!

6. **[4.0新增]** 根据图片消息发送的时间, 去QQ的图片缓存目录查找同时创建的文件, 实现**能查看撤回的图片!**

7. **[4.0新增]** 把联系人列表存入set, 即使不是和当前联系人发来的消息也能截获

8. **[4.0新增]** 更完善的查找算法, 即使一次撤回10条也能不怕

9. **免Root!** 

10. **免Root!**

<hr>

#### 快去下载体验吧

  
  
