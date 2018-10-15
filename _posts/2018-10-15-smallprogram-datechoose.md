小程序1-日期选择器
===

.js

```javascript
  bindDateChange: function (e) {
    console.log(e.detail.value)
    var timestamp2 = Date.parse(new Date(e.detail.value));
    timestamp2 = timestamp2 / 1000;
    //2014-07-10 10:21:12的时间戳为：1404958872 
    console.log(e.detail.value + "的时间戳为：" + timestamp2);

    this.setData({
      dates: e.detail.value
    })
  },

```

```javascript
on Ready function(){
var timestamp = Date.parse(new Date());
    timestamp = timestamp / 1000;
    console.log("当前时间戳为：" + timestamp);
    var n = timestamp * 1000;
    var date = new Date(n);
    //年
    var Y = date.getFullYear();
    //月
    var M = (date.getMonth() + 1 < 10 ? '0' + (date.getMonth() + 1) : date.getMonth() + 1);
    //日
    var D = date.getDate() < 10 ? '0' + date.getDate() : date.getDate();
    //时
    var h = date.getHours();
    //分
    var m = date.getMinutes();
    //秒
    var s = date.getSeconds();

    console.log("当前时间：" + Y + M + D +" " + h + ":" + m + ":" + s);
  },

  bindDateChange: function (e) {
    console.log(e.detail.value)
    var timestamp2 = Date.parse(new Date(e.detail.value));
    timestamp2 = timestamp2 / 1000;
    //2014-07-10 10:21:12的时间戳为：1404958872 
    console.log(e.detail.value + "的时间戳为：" + timestamp2);

    this.setData({
      dates: e.detail.value
    })
},
```

```javascript
  data:{dates: '2016-11-08',
    times: '12:00',
}
```
.wxml

```html
  <view class="section">  
  <picker mode="date" value="{{date}}"  bindchange="bindDateChange">  
    <view class="picker">  
      日期: {{dates}}  
    </view>  
  </picker>  
</view> 
```
.wxss

```css
.section{
   background:whitesmoke;
   margin:20rpx;
   padding:20rpx;
   width: 330rpx;
   height: 35rpx;
}
```

