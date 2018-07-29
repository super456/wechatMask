在工作中经常会用到遮罩层弹窗，所以简单分享一下，之前写过的一个弹出广告图片遮罩层功能demo。

### （一）实现效果
![实现效果](http://pbr0erxxq.bkt.clouddn.com/2018-07-29/wechatMask.gif)

### （二）实现过程
实现过程主要是设置css样式，比较容易理解。
1、设置wxml代码布局：设置一个背景布局：用来显示灰色背景；嵌套一个显示展示图片容器，嵌套一个显示闭关按钮的容器。
   

```
   <view class="b1" hidden="{{flag}}">
		<view class="b2">
			<image src='../../images/test.jpg'/>
		</view>
		  <view class="t_w">
		   <cover-view class="t_image" bindtap="closeMask">
		     <cover-image  src="../../images/qcm.png"></cover-image>
		    </cover-view>
		  </view>
	</view>
```

 2、wxss样式设置：

```
/* 设置背景遮罩层样式 */
.b1 {
  position: fixed;
  width: 100%;
  height: 100%;
  top: 0;
  background: rgba(0, 0, 0, 0.4);
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
/* 设置展示图片大小 */
.b2 {
  width: 50%;
  height: 50%;
}
/* 设置展示图片与关闭按钮图片的距离 */
.t_w {
  margin-top: 20rpx;
}
/* 设置关闭按钮图片显示的大小 */
.b2 image {
  width: 100%;
  height: 100%;
}
/* 设置关闭按钮宽高 */
.t_image {
  width: 60rpx;
  height: 60rpx;
}
```

3、 js两个方法控制显示与关闭操作：

```
 data: {
    motto: '微信遮罩层显示',
   flag: true,
  },
  showMask:function(){
    this.setData({ flag: false })
  },
  closeMask: function () {
    this.setData({ flag: true })
  },
})
```
### （三）完整代码
[代码下载](https://github.com/super456/wechatMask)
