# InputWidget
一个适用于微信小程序的输入组件, 可以发送文字，语音， 图片

# 效果
<image src="/picture/GIF.gif" width="300"/>

### 切换到文字
<image src="/picture/1.png" width="300"/>

### 切换到语音
<image src="/picture/2.png" width="300"/>

### 录音
<image src="/picture/3.png" width="300"/>

### 取消录音
<image src="/picture/4.png" width="300"/>




# 使用
文件置于components/customeSessionWidget文件夹下面  
在所需要页面json文件引用改自定义组件, 路径根据具体文件结构决定
```
"usingComponents": {
    "customeSessionWidget": "../../components/customeSessionWidget/customeSessionWidget",
  }
```

在页面的wxml中使用该自定义组件
```
<customeSessionWidget bindsend="send" id="sessionWidget"></customeSessionWidget>
```

需要绑定send事件， 该事件会在确认发送文字，确认发送图片, 以及确认发送语音时触发

根据发送的不同内容, 事件对象分别如下:(通过e.detail获取)  
```
{ 
  content: 'xxxxx', 
  type: 'text' 
}
{ 
  tempFilePaths: [path1, path2], 
  type: 'picture' 
}
{ 
  tempFilePath: path, 
  type: 'voice' 
}
```
