# mui示例
mui开源框架
# 基础布局 #
1. 头部
核心css `mui-bar` `mui-bar-nav`
```html
<header class="mui-bar mui-bar-nav">
    <a class="mui-action-back mui-icon mui-icon-left-nav mui-pull-left"></a>
    <h1 class="mui-title">hello</h1>
</header>
```
2. 主体部分
核心css `mui-content`
```html
<div class="mui-content">
    主体部分....
</div>
```
##### 完整代码演示
```html
<!DOCTYPE html>
<html>
  <head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width,initial-scale=1,minimum-scale=1,maximum-scale=1,user-scalable=no" />
  <title></title>
  <script src="js/mui.min.js"></script>
  <link href="css/mui.min.css" rel="stylesheet"/>
    <script type="text/javascript" charset="utf-8">
      mui.init();
    </script>
  </head>
  <body>
  <div>
  <header class="mui-bar mui-bar-nav">
      <a class="mui-action-back mui-icon mui-icon-left-nav mui-pull-left"></a>
      <h1 class="mui-title">hello</h1>
  </header>
  <div class="mui-content">
      内容部分....
  </div>
  </body>
</html>
```
3. 折叠面板
折叠面板从二级列表中演化而来，dom结构和二级列表类似，如下：
```html
<ul class="mui-table-view"> 
    <li class="mui-table-view-cell mui-collapse">
      <a class="mui-navigate-right" href="#">面板1</a>
      <div class="mui-collapse-content">
      <p>面板1子内容</p>
      </div>
    </li>
</ul>
```
可以在折叠面板中放置任何内容；折叠面板默认收缩，若希望某个面板默认展开，只需要在包含`.mui-collapse`类的`li`节点上，
增加`.mui-active`类即可；mui官网中的方法说明，使用的就是折叠面板控件。
##### 注意事项：
  1、折叠面板布局必须在`mui-content`下
  2、外层使用 `mui-card` 包裹产生边缘
# 完整代码
```html
<header class="mui-bar mui-bar-nav">
    <a class="mui-action-back mui-icon mui-icon-left-nav mui-pull-left"></a>
    <h1 class="mui-title">hello</h1>
</header>
<div class="mui-content">
    <div class="mui-card">
        <ul class="mui-table-view"> 
            <li class="mui-table-view-cell mui-collapse">
              <a class="mui-navigate-right" href="#">面板1</a>
              <div class="mui-collapse-content">
              <p>面板1子内容</p>
              </div>
            </li>
        </ul>
    </div>
</div>
```
4. 按钮
mui默认按钮为灰色，另外还提供了蓝色（blue）、绿色(green)、黄色(yellow)、红色(red)、紫色(purple)五种色系 的按钮，五种色系对应五种场景，
分别为`primary`、`success`、`warning`、`danger`、`royal`；使用`.mui-btn`类即可生成一个 默认按钮，继续添加`.mui-btn-`颜色值或`.mui-btn-`
场景可生成对应色系的按钮，例如：通过.mui-btn-blue或.mui-btn- primary均可生成蓝色按钮；

普通按钮在`button`节点上增加`.mui-btn`类，即可生成默认按钮；若需要其他颜色的按钮，则继续增加对应`class`即可，比如`.mui-btn-blue`即可变成蓝
色按钮
```html
<button type="button" class="mui-btn">默认</button>
<button type="button" class="mui-btn mui-btn-primary">蓝色</button>
<button type="button" class="mui-btn mui-btn-success">绿色</button>
<button type="button" class="mui-btn mui-btn-warning">黄色</button>
<button type="button" class="mui-btn mui-btn-danger">红色</button>
<button type="button" class="mui-btn mui-btn-royal">紫色</button>
```
若希望无底色、有边框的按钮，仅需增加`.mui-btn-outlined`类即可，代码如下：
```html
<button type="button" class="mui-btn mui-btn-outlined">默认</button>
<button type="button" class="mui-btn mui-btn-primary mui-btn-outlined">蓝色</button>
<button type="button" class="mui-btn mui-btn-success mui-btn-outlined">绿色</button>
<button type="button" class="mui-btn mui-btn-warning mui-btn-outlined">黄色</button>
<button type="button" class="mui-btn mui-btn-danger mui-btn-outlined">红色</button>
<button type="button" class="mui-btn mui-btn-royal mui-btn-outlined">紫色</button>
```
5. 操作表
`actionsheet`一般从底部弹出，显示一系列可供用户选择的操作按钮；` actionsheet`是从`popover`控件基础上演变而来，实际上就是一个固定从底部弹出的`popover`，故DOM结构和`popove`类似，只是需要在含`.mui-popover`类的节点上增加`.mui-popover-bottom`、`.mui-popover-action`类；
```html
<div id="sheet1" class="mui-popover mui-popover-bottom mui-popover-action ">
    <!-- 可选择菜单 -->
    <ul class="mui-table-view">
      <li class="mui-table-view-cell">
        <a href="#">菜单1</a>
      </li>
      <li class="mui-table-view-cell">
        <a href="#">菜单2</a>
      </li>
    </ul>
    <!-- 取消菜单 -->
    <ul class="mui-table-view">
      <li class="mui-table-view-cell">
        <a href="#sheet1"><b>取消</b></a>
      </li>
    </ul>
</div>
```
推荐使用锚点方式显示、隐藏`actionsheet`；若要使用js代码动态显示、隐藏`actionsheet`，同样在`popover`插件的构造方法中传入`"toggle"`参数即可，
如下：
注意：传入toggle参数，用户无需关心当前是显示还是隐藏状态，mui会自动识别处理；
```javascript
mui('#sheet1').popover('toggle');
```
##### 完整代码
```html
<header class="mui-bar mui-bar-nav">
    <a class="mui-action-back mui-icon mui-icon-left-nav mui-pull-left"></a>
    <h1 class="mui-title">hello</h1>
</header>
<div class="mui-content">
    <div style="padding:20px;">
        <input type="button" class="mui-btn-blue" value="点击这里弹出操作菜单" onclick="showPop();" />
    </div>
</div>
<div id="sheet1" class="mui-popover mui-popover-bottom mui-popover-action ">
    <!-- 可选择菜单 -->
    <ul class="mui-table-view">
      <li class="mui-table-view-cell">
        <a href="#">菜单1</a>
      </li>
      <li class="mui-table-view-cell">
        <a href="#">菜单2</a>
      </li>
    </ul>
    <!-- 取消菜单 -->
    <ul class="mui-table-view">
      <li class="mui-table-view-cell">
        <a href="#sheet1"><b>取消</b></a>
      </li>
    </ul>
</div>
<script type="text/javascript">
function showPop(){
    mui('#sheet1').popover('toggle');
}
</script>
```
6. 数字角标
数 字角标一般和其它控件（列表、9宫格、选项卡等）配合使用，用于进行数量提示。 角标的核心类是`.mui-badge`，默认为实心灰色背景；同时，mui还内置
了蓝色（blue）、绿色(green)、黄色(yellow)、红色 (red)、紫色(purple)五种色系的数字角标，如下：
```html
<span class="mui-badge mui-badge-inverted">1</span>
<span class="mui-badge mui-badge-primary mui-badge-inverted">2</span>
<span class="mui-badge mui-badge-success mui-badge-inverted">3</span>
<span class="mui-badge mui-badge-warning mui-badge-inverted">4</span>
<span class="mui-badge mui-badge-danger mui-badge-inverted">5</span>
<span class="mui-badge mui-badge-royal mui-badge-inverted">6</span>
```
若无需底色，则增加`.mui-badge-inverted`类即可，如下：
```html
<span class="mui-badge mui-badge-inverted">1</span>
<span class="mui-badge mui-badge-primary mui-badge-inverted">2</span>
<span class="mui-badge mui-badge-success mui-badge-inverted">3</span>
<span class="mui-badge mui-badge-warning mui-badge-inverted">4</span>
<span class="mui-badge mui-badge-danger mui-badge-inverted">5</span>
<span class="mui-badge mui-badge-royal mui-badge-inverted">6</span>
```
7. 复选框
`checkbox`常用于多选的情况，比如批量删除、添加等；
##### DOM结构
```html
<div class="mui-input-row mui-checkbox">
    <label>checkbox示例</label>
    <input name="checkbox1" value="Item 1" type="checkbox" checked>
</div>
```
默认`checkbox`在右侧显示，若希望在左侧显示，只需增加`.mui-left`类即可，如下：
```html
<div class="mui-input-row mui-checkbox mui-left">
    <label>checkbox左侧显示示例</label>
    <input name="checkbox1" value="Item 1" type="checkbox">
</div>
```
若要禁用`checkbox`，只需在`checkbox`上增加`disabled`属性即可；
8. 单选框
`radio`用于单选的情况
DOM结构
```html
<div class="mui-input-row mui-radio">
    <label>radio</label>
    <input name="radio1" type="radio">
</div>
```
默认`radio`在右侧显示，若希望在左侧显示，只需增加`.mui-left`类即可，如下：
```html
<div class="mui-input-row mui-radio mui-left">
    <label>radio</label>
    <input name="radio1" type="radio">
</div>
```
若要禁用`radio`，只需在`radio`上增加`disabled`属性即可；
mui基于列表控件，提供了列表式单选实现；在列表根节点上增加`.mui-table-view-radio`类即可，若要默认选中某项，只需要在对应li节点上增加
`.mui-selected`类即可，dom结构如下：
```html
<ul class="mui-table-view mui-table-view-radio">
    <li class="mui-table-view-cell">
        <a class="mui-navigate-right">Item 1</a>
    </li>
    <li class="mui-table-view-cell mui-selected">
        <a class="mui-navigate-right">Item 2</a>
    </li>
    <li class="mui-table-view-cell">
        <a class="mui-navigate-right">Item 3</a>
    </li>
</ul>
```
列表式单选在切换选中项时会触发`selected`事件，在事件参数`（e.detail.el）`中可以获得当前选中的dom节点，如下代码打印当前选中项的`innerHTML`：
```javascript
var list = document.querySelector('.mui-table-view.mui-table-view-radio');
list.addEventListener('selected',function(e){
    console.log("当前选中的为："+e.detail.el.innerText);
});
```
9. js获取单选按钮的值
```javascript
function getVals(){
    var res = getRadioRes('rds');
    if(res == null){mui.toast('请选择'); return;}
    mui.toast(res);
}
function getRadioRes(className){
    var rdsObj = document.getElementsByClassName(className);
    var checkVal = null;
    for(i = 0; i < rdsObj.length; i++){
        if(rdsObj[i].checked){checkVal = rdsObj[i].value;}
    }
    return checkVal;
}
</script>
```
10. js获取复选框的值
```javascript
function getVals(){
    var res = getCheckBoxRes('rds');
    if(res.length < 1){
        mui.toast('请选择');
        return;
    }
    mui.toast(res);
}
function getCheckBoxRes(className){
    var rdsObj   = document.getElementsByClassName(className);
    var checkVal = new Array();
    var k        = 0;
    for(i = 0; i < rdsObj.length; i++){
        if(rdsObj[i].checked){
            checkVal[k] = rdsObj[i].value;
            k++;
        }
    }
    return checkVal;
}
```
11. 时间选择器
##### 完整代码：
```html
<header class="mui-bar mui-bar-nav">
    <a class="mui-action-back mui-icon mui-icon-left-nav mui-pull-left"></a>
    <h1 class="mui-title">hello</h1>
</header>
<div class="mui-content">
    <div style="padding:15px;">
        <button id='pickDateBtn' type="button" class="mui-btn">选择日期</button>
    </div>
    <div style="padding:15px;">
        <button id='pickTimeBtn' type="button" class="mui-btn">选择时间</button>
    </div>
</div>
<script type="text/javascript">
document.getElementById("pickDateBtn").addEventListener('tap', function() {
    var dDate = new Date();
    //设置当前日期（不设置默认当前日期）
    dDate.setFullYear(2016, 7, 16);
    var minDate = new Date();
    //最小时间
    minDate.setFullYear(2010, 0, 1);
    var maxDate = new Date();
    //最大时间
    maxDate.setFullYear(2016, 11, 31);
    plus.nativeUI.pickDate(function(e) {
        var d = e.date;
        mui.toast('您选择的日期是:' + d.getFullYear() + "-" + (d.getMonth() + 1) + "-" + d.getDate());
    }, function(e) {
        mui.toast("您没有选择日期");
    }, {
        title: '请选择日期',
        date: dDate,
        minDate: minDate,
        maxDate: maxDate
    });
});
document.getElementById("pickTimeBtn").addEventListener('tap', function() {
    var dTime = new Date();
    //设置默认时间
    dTime.setHours(6, 0);
    plus.nativeUI.pickTime(function(e) {
        var d = e.date;
        mui.toast("您选择的时间是：" + d.getHours() + ":" + d.getMinutes());
    }, function(e) {
        mui.toast("您没有选择时间");
    }, {
        title: "请选择时间",
        is24Hour: true,
        time: dTime
    });
});
```
##### js获取当前时间
```
var myDate = new Date();
myDate.getYear();        //获取当前年份(2位)
myDate.getFullYear();    //获取完整的年份(4位,1970-????)
myDate.getMonth();       //获取当前月份(0-11,0代表1月)
myDate.getDate();        //获取当前日(1-31)
myDate.getDay();         //获取当前星期X(0-6,0代表星期天)
myDate.getTime();        //获取当前时间(从1970.1.1开始的毫秒数)
myDate.getHours();       //获取当前小时数(0-23)
myDate.getMinutes();     //获取当前分钟数(0-59)
myDate.getSeconds();     //获取当前秒数(0-59)
myDate.getMilliseconds();    //获取当前毫秒数(0-999)
myDate.toLocaleDateString();     //获取当前日期
var mytime=myDate.toLocaleTimeString();     //获取当前时间
myDate.toLocaleString( );        //获取日期与时间
```
12. `mui.alert()` 普通提醒
##### 参数
```
1.message Type: String 提示对话框上显示的内容
2.title Type: String 提示对话框上显示的标题
3.btnValue Type: String 提示对话框上按钮显示的内容
4.callback Type: Function 提示对话框上关闭后的回调函数
5.type Value: 'div'是否使用h5绘制的对话框
```
##### 演示代码
```javascript
mui.alert('欢迎使用Hello Word', 'Hello Word', function() {
   mui.toast('你刚关闭了警告框');
});
```
13. `mui.confirm()` 确定消息框
##### 参数
```
1.message Type: String 提示对话框上显示的内容
2.title Type: String提示对话框上显示的标题
3.btnValue Type: Array 提示对话框上按钮显示的内容
4.callback Type: Function 提示对话框上关闭后的回调函数
5.type Value: 'div' 是否使用h5绘制的对话框
```
##### 演示代码
```javascript
var btnArray = ['取消', '确定'];
mui.confirm('真的要删除吗？','Hi...',new Array('否','是'),function(e){
   if(e.index == 1){mui.toast('是');}else{mui.toast('否');}
});
```
14. `mui.prompt()` 输入框
##### 参数
```
1.message Type: String 提示对话框上显示的内容
2.placeholder Type: String 编辑框显示的提示文字
3.title Type: String 提示对话框上显示的标题
4.btnValue Type: Array 提示对话框上按钮显示的内容
5.callback Type: Function提示对话框上关闭后的回调函数
6.type Value: 'div' 是否使用h5绘制的对话框
```
##### 演示代码
```javascript
var btnArray = ['取消', '确定'];
mui.prompt('请输入您的姓名？','Hi...',new Array('取消','确定'),function(e){
    if(e.index == 1){
        mui.toast(e.value);
    }else{
        mui.toast('您取消了输入');
    }
});
```
15. `mui.toast()` 自动消失的消息框
```javascript
mui.toast('hi...');
```
16. 表单元素
基本说明:所有包裹在`.mui-input-row` 类中的 `input`、`textarea`等元素都将被默认设置宽度属性为w`idth: 100%`; 将 `label `元素和上述控件控件包裹
在`.mui-input-group`中可以获得最好的排列。
```html
<form class="mui-input-group">
    <div class="mui-input-row">
        <label>用户名</label>
    <input type="text" class="mui-input-clear" placeholder="请输入用户名">
    </div>
    <div class="mui-input-row">
        <label>密码</label>
        <input type="password" class="mui-input-password" placeholder="请输入密码">
    </div>
    <div class="mui-button-row">
        <button type="button" class="mui-btn mui-btn-primary" >确认</button>
        <button type="button" class="mui-btn mui-btn-danger" >取消</button>
    </div>
</form>
```
##### 输入增强
mui目前提供的输入增强包括：快速删除、语音输入`*5+ only`和密码框显示隐藏密码。
1.快速删除：只需要在`input`控件上添加`.mui-input-clear`类，当`input` 控件中有内容时，右侧会有一个删除图标，点击会清空当前`input`的内容；
```html
<form class="mui-input-group">
    <div class="mui-input-row">
        <label>快速删除</label>
        <input type="text" class="mui-input-clear" placeholder="请输入内容">
    </div>
</form>
```
2.搜索框：在`.mui-input-row`同级添加`.mui-input-search` 类，就可以使用`search`控件
```javascript
<form class="mui-input-group">
    <div class="mui-input-row mui-search">
        <input type="search" class="mui-input-clear" placeholder="hcoder">
    </div>
</form>
```
3.密码框：给`input`元素添加`.mui-input-password`类即可使用
```html
<form class="mui-input-group">
    <div class="mui-input-row">
        <label>密码框</label>
        <input type="password" class="mui-input-password" placeholder="请输入密码">
    </div>
</form>
```
##### 初始化
mui在`mui.init()`中会自动初始化基本控件,但是 动态添加的元素需要重新进行初始化
```javascript
mui('.mui-input-row input').input();
```
17. 轮播组件
轮播组件是mui提供的一个核心组件，在该核心组件基础上，衍生出了图片轮播、可拖动式图文表格、可拖动式选项卡、左右滑动9宫格等组件，这些组件有较多
共同点。
##### Dom构造：
```javascript
<div class="mui-slider">
  <div class="mui-slider-group">
    <!--第一个内容区容器-->
    <div class="mui-slider-item">
      <!-- 具体内容 -->
    </div>
    <!--第二个内容区-->
    <div class="mui-slider-item">
      <!-- 具体内容 -->
    </div>
  </div>
</div>
```
##### js部分
```
mui.plusReady(function(){
    //获得slider插件对象
    var gallery = mui('.mui-slider');
        gallery.slider({
  	    interval:5000//自动轮播周期，若为0则不自动播放，默认为0；
    });
});
```
##### 显示圆点
```html
<div class="mui-slider-indicator">
    <div class="mui-indicator mui-active"></div>
    <div class="mui-indicator"></div>
</div>
```
##### 轮播循环
若要支持循环，则需要在`.mui-slider-group`节点上增加`.mui-slider-loop`类，同时需要重复增加2张图片，图片顺序变为：4、1、2、3、4、1，代码
示例如下：
```html
<div class="mui-slider">
  <div class="mui-slider-group mui-slider-loop">
    <!--支持循环，需要重复图片节点-->
    <div class="mui-slider-item mui-slider-item-duplicate"><a href="#"><img src="4.jpg" /></a></div>
    <div class="mui-slider-item"><a href="#"><img src="1.jpg" /></a></div>
    <div class="mui-slider-item"><a href="#"><img src="2.jpg" /></a></div>
    <div class="mui-slider-item"><a href="#"><img src="3.jpg" /></a></div>
    <div class="mui-slider-item"><a href="#"><img src="4.jpg" /></a></div>
    <!--支持循环，需要重复图片节点-->
    <div class="mui-slider-item mui-slider-item-duplicate"><a href="#"><img src="1.jpg" /></a></div>
  </div>
</div>
```
##### 轮播跳转
若要跳转到第x张图片，则可以使用图片轮播插件的`gotoItem`方法，例如：
```javascript
var gallery = mui('.mui-slider');
gallery.slider().gotoItem(index);//跳转到第index张图片，index从0开始；
```
##### 轮播事件
当拖动切换显示内容时，会触发slide事件，通过该事件的`detail.slideNumber`参数可以获得当前显示项的索引（第一项索引为0，第二项为1，以此类推），
利用该事件，可在显示内容切换时，动态处理一些业务逻辑。

如下为一个可拖动式选项卡示例，为提高页面加载速度，页面加载时，仅显示第一个选项卡的内容，第二、第三选项卡内容为空。
当切换到第二、第三个选项卡时，再动态获取相应内容进行显示：
```javascript
var item2Show = false,item3Show = false;//子选项卡是否显示标志
document.querySelector('.mui-slider').addEventListener('slide', function(event) {
  if (event.detail.slideNumber === 1&&!item2Show) {
    //切换到第二个选项卡
    //根据具体业务，动态获得第二个选项卡内容；
    var content = ....
    //显示内容
    document.getElementById("item2").innerHTML = content;
    //改变标志位，下次直接显示
    item2Show = true;
  } else if (event.detail.slideNumber === 2&&!item3Show) {
    //切换到第三个选项卡
    //根据具体业务，动态获得第三个选项卡内容；
    var content = ....
    //显示内容
    document.getElementById("item3").innerHTML = content;
    //改变标志位，下次直接显示
    item3Show = true;
  }
});
```
18. 普通列表
列表是常用的UI控件，mui封装的列表组件比较简单，只需要在`ul`节点上添加`.mui-table-view`类、在`li`节点上添加`.mui-table-view-cell`类即可，
如下为示例代码
```html
<ul class="mui-table-view">
    <li class="mui-table-view-cell">Item 1</li>
    <li class="mui-table-view-cell">Item 2</li>
    <li class="mui-table-view-cell">Item 3</li>
</ul>
```
若右侧需要增加导航箭头，变成导航链接，则只需在`li`节点下增加`a`子节点，并为该`a`节点增加`.mui-navigate-right`类即可，如下：
```html
<ul class="mui-table-view">
    <li class="mui-table-view-cell"><a class="mui-navigate-right">Item 1</a></li>
    <li class="mui-table-view-cell"><a class="mui-navigate-right">Item 2</a></li>
    <li class="mui-table-view-cell"><a class="mui-navigate-right">Item 3</a></li>
</ul>
```
mui支持将数字角标、按钮、开关等控件放在列表中；mui默认将数字角标放在列表右侧显示，代码如下：
```html
<ul class="mui-table-view">
    <li class="mui-table-view-cell">Item 1<span class="mui-badge mui-badge-primary">11</span></li>
    <li class="mui-table-view-cell">Item 2<span class="mui-badge mui-badge-success">22</span></li>
    <li class="mui-table-view-cell">Item 3<span class="mui-badge">33</span></li>
</ul>
```
19. 图文列表
图文列表继承自列表组件，主要添加了`.mui-media`、`.mui-media-object`、`.mui-media-body`几个类，如下为示例代码：
```html
<ul class="mui-table-view">
  <li class="mui-table-view-cell mui-media">
    <a href="javascript:;">
      <img class="mui-media-object mui-pull-left" src="imgs/1.jpg">
      <div class="mui-media-body">
          幸福
        <p class='mui-ellipsis'>能和心爱的人一起睡觉，是件幸福的事情；可是，打呼噜怎么办？</p>
      </div>
    </a>
  </li>
  <li class="mui-table-view-cell mui-media">
    <a href="javascript:;">
      <img class="mui-media-object mui-pull-left" src="imgs/1.jpg">
      <div class="mui-media-body">
          木屋
        <p class='mui-ellipsis'>想要这样一间小木屋，夏天挫冰吃瓜，冬天围炉取暖.</p>
      </div>
    </a>
  </li>
</ul>
```
20. 有准确值的进度条
有准确值的进度条会显示当前进度正处于整体进度的占比位置，用户可以更直观的预期完成时间；使用进度条控件，需要一个进度条控件容器，mui会自动识
别该容器下是否有进度条控件，若没有，则自动创建。进度条控件DOM结构：
```html
<div id="demo1" class="mui-progressbar">
    <span></span>
</div>
```
初始化:
```javascript
mui(container).progressbar({progress:20}).show();
```
`progressbar`初始化逻辑：
检查当前容器(`container`控件)自身是否包含`.mui-progressbar`类：
当前容器包含`.mui-progressbar`类，则以当前容器为目标控件，直接显示进度；
否则，检查当前容器的直接孩子节点是否包含`.mui-progressbar`类，若存在，则以遍历到的第一个含有`.mui-progressbar`类的孩子节点为目标控件，
显示进度；若当前容器的直接孩子节点，均不含`.mui-progressbar`类,则自动创建进度条控件；
更改显示进度条:
```javascript
mui(container).progressbar().setProgress(50);
```
关闭进度条:
```javascript
mui(container).progressbar().hide();
```
备注：关闭进度条一般用于动态创建（DOM中预先未定义）的进度条，调用`hide`方法后，会直接删掉对应的DOM节点；若已提前创建好DOM节点的进度条，
调用`hide`方法无效；
21. 滑块
```html
<div class="mui-input-row mui-input-range">
    <label>Range</label>
    <input type="range" min="0" max="100">
</div>
```
获取滑块数值的样例代码
```javascript
<div class="mui-content">
<div class="mui-input-row mui-input-range">
    <label>Range</label>
    <input type="range" min="0" max="100" id="range1">
</div>
<div style="padding:20px;">
    <input type="button" class="mui-btn" value="获取滑块值" onclick="getVal();" />
</div>
</div>
<script>
function getVal(){
    var rangeObj = mui('#range1');
    mui.toast(rangeObj[0].value);
}
```
22. switch 开关
mui提供了开关控件，点击滑动两种手势都可以对开关控件进行操作,默认开关控件,带`on`/`off`文字提示，打开时为绿色背景，基本`class`类为`.mui-switch`、
`.mui-switch-handle`，DOM结构如下：
```html
<div class="mui-switch">
  <div class="mui-switch-handle"></div>
</div>
```
若希望开关默认为打开状态，只需要在`.mui-switch`节点上增加`.mui-active`类即可，如下：
```html
<!-- 开关打开状态，多了一个.mui-active类 -->
<div class="mui-switch mui-active">
  <div class="mui-switch-handle"></div>
</div>
```
若希望隐藏`on`/`off`文字提示，变成简洁模式，需要在`.mui-switch`节点上增加`.mui-switch-mini`类，如下：
```html
<!-- 简洁模式开关关闭状态 -->
<div class="mui-switch mui-switch-mini">
  <div class="mui-switch-handle"></div>
</div>
<!-- 简洁模式开关打开状态 -->
<div class="mui-switch mui-switch-mini mui-active">
  <div class="mui-switch-handle"></div>
</div>
```
mui默认还提供了蓝色开关控件，只需在`.mui-switch`节点上增加`.mui-switch-blue`类即可，如下：
```html
<!-- 蓝色开关关闭状态 -->
<div class="mui-switch mui-switch-blue">
  <div class="mui-switch-handle"></div>
</div>
<!-- 蓝色开关打开状态 -->
<div class="mui-switch mui-switch-blue mui-active">
  <div class="mui-switch-handle"></div>
</div>
```
蓝色开关上增加`.mui-switch-mini`即可变成无文字的简洁模式

若要获得当前开关状态，可通过判断当前开关控件是否包含`.mui-active`类来实现，若包含，则为打开状态，否则即为关闭状态；
如下为代码示例：
```javascript
var isActive = document.getElementById("mySwitch").classList.contains("mui-active");
if(isActive){
  console.log("打开状态");
}else{
  console.log("关闭状态");  
}
```
若使用js打开、关闭开关控件，可使用`switch`插件的`toggle()`方法，如下为示例代码：
```javascript
mui("#mySwitch").switch().toggle();
```
##### 事件
开关控件在打开/关闭两种状态之间进行切换时，会触发`toggle`事件,通过事件的`detail.isActive`属性可以判断当前开关状态。可通过监听`toggle`事件，可
以在开关切换时执行特定业务逻辑。
如下为使用示例：
```javascript
document.getElementById("mySwitch").addEventListener("toggle",function(event){
  if(event.detail.isActive){
    console.log("你启动了开关");
  }else{
    console.log("你关闭了开关");  
  }
})
```
23. cardview（卡片视图）
使用`mui-card`类即可生成一个卡片容器，卡片视图主要有页眉、内容区、页脚三部分组成，结构如下：
```html
<div class="mui-card">
    <!--页眉，放置标题-->
    <div class="mui-card-header">页眉</div>
    <!--内容区-->
    <div class="mui-card-content">内容区</div>
    <!--页脚，放置补充信息或支持的操作-->
    <div class="mui-card-footer">页脚</div>
</div>
```
卡片页眉及内容区，均支持放置图片； 页眉放置图片的话，需要在`.mui-card-header`节点上增加`.mui-card-media`类，然后设置一张图片做背景图即可，
代码如下：
```html
<div class="mui-card-header mui-card-media" style="height:40vw;background-image:url(./liyaxin.jpg)"></div>
```
若希望在页眉放置更丰富的信息，比如头像、主标题、副标题，则需使用`.mui-media-body`类，示例代码如下：
```html
<div class="mui-card-header mui-card-media">
    <img src="../images/logo.png" />
    <div class="mui-media-body">
        小M
	<p>发表于 2016-06-30 15:30</p>
    </div>
</div>
```
##### 小技巧
图片出现默认的空白解决方案：
```css
    line-height:0px;
```
24. mask（遮罩蒙版）
在`popover`、侧滑菜单等界面，经常会用到蒙版遮罩；比如`popover`弹出后，除`popover`控件外的其它区域都会遮罩一层蒙版，用户点击蒙版不会触发蒙版下方
的逻辑，而会关闭`popover`同时关闭蒙版；再比如侧滑菜单界面，菜单划出后，除侧滑菜单之外的其它区域都会遮罩一层蒙版，用户点击蒙版会关闭侧滑菜单同时关
闭蒙版。
遮罩蒙版常用的操作包括：创建、显示、关闭，如下代码：
```javascript
var mask = mui.createMask(callback);//callback为用户点击蒙版时自动执行的回调；
mask.show();//显示遮罩
mask.close();//关闭遮罩
```
注意：关闭遮罩仅会关闭，不会销毁；关闭之后可以再次调用`mask.show();`打开遮罩；
mui默认的蒙版遮罩使用`.mui-backdrop`类定义（如下代码），若需自定义遮罩效果，只需覆盖定义`.mui-backdrop`即可；
```css
.mui-backdrop {position: fixed;top: 0;right: 0;bottom: 0;left: 0;z-index: 998;background-color: rgba(0,0,0,.3);}
```
25. mui插件初始化
使用 `mui.init();` 进行mui插件初始化。
26. 页面初始化
在app开发中，若要使用HTML5+扩展api，必须等`plusready`事件发生后才能正常使用，mui将该事件封装成了`mui.plusReady()`方法，涉及到HTML5+的api，
建议都写在`mui.plusReady`方法中。如下为打印当前页面URL的示例：
```javascript
mui.plusReady(function(){
     console.log("当前页面URL："+plus.webview.currentWebview().getURL());
});
```
27. 创建子页面
在移动app开发过程中，经常遇到卡头卡尾的页面，此时若使用局部滚动，在android手机上会出现滚动不流畅的问题； mui的解决思路是：将需要滚动的区域通过
单独的`webview`实现，完全使用原生滚动。具体做法则是：将目标页面分解为主页面和内容页面，主页面显示卡头卡尾区域，比如顶部导航、底部选项卡等；内容页
面显示具体需要滚动的内容，然后在主页面中调用`mui.init`方法初始化内容页面。
```javascript
mui.init({
    subpages:[{
        url:your-subpage-url,//子页面HTML地址，支持本地地址和网络地址
        id:your-subpage-id,//子页面标志
        styles:{
            top:subpage-top-position,//子页面顶部位置
            bottom:subpage-bottom-position,//子页面底部位置
            width:subpage-width,//子页面宽度，默认为100%
            height:subpage-height,//子页面高度，默认为100%
        },
    extras:{}//额外扩展参数
    }]
});
```
参数说明：`styles`表示窗口属性，参考5+规范中的`WebviewStyle`；特别注意，`height`和`width`两个属性,即使不设置，也默认按100%计算；因此若设置了
`top`值为非`"0px"`的情况，建议同时设置`bottom`值，否则5+ runtime根据高度100%计算，可能会造成页面真实底部位置超出屏幕范围的情况；`left`、`right`
同理。
##### 代码样例
主页面index.html
```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width,initial-scale=1,minimum-scale=1,maximum-scale=1,user-scalable=no" />
        <title></title>
        <script src="js/mui.min.js"></script>
        <link href="css/mui.min.css" rel="stylesheet"/>
    </head>
<body>
    <header class="mui-bar mui-bar-nav">
        <a class="mui-action-back mui-icon mui-icon-left-nav mui-pull-left"></a>
        <h1 class="mui-title">hello</h1>
    </header>
</body>
<script type="text/javascript">
mui.init({
     subpages:[{
         url   :'liyaxin.html',
         id    : 'liyaxin.html',
         styles:{
            top    : '45px',//子页面顶部位置
            bottom : '0px',//子页面底部位置
            width  : '100%',
            height : '100%'
          },
     }]
});
</script>
</html>
```
子页面 liyaxin.html
```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width,initial-scale=1,minimum-scale=1,maximum-scale=1,user-scalable=no" />
        <title></title>
        <script src="js/mui.min.js"></script>
        <link href="css/mui.min.css" rel="stylesheet"/>
        <script type="text/javascript" charset="utf-8">
        mui.init();
        </script>
    </head>
<body>
<div class="mui-content">
    <div class="mui-card">
        <!--页眉，放置标题-->
        <div class="mui-card-header mui-card-media">
            <img src="imgs/logo.png" />
            <div class="mui-media-body">
                小M
                <p>发表于 2016-06-30 15:30</p>
            </div>
        </div>
        <!--内容区-->
        <div class="mui-card-content" style="overflow:hidden; padding:0px; line-height:0px;">
            <img src="imgs/1.jpg" width="100%" />
        </div>
        <!--页脚，放置补充信息或支持的操作-->
        <div class="mui-card-footer">页脚</div>
    </div>
    <div class="mui-card">
        <!--页眉，放置标题-->
        <div class="mui-card-header mui-card-media">
            <img src="imgs/logo.png" />
            <div class="mui-media-body">
                小M
                <p>发表于 2016-06-30 15:30</p>
            </div>
        </div>
        <!--内容区-->
        <div class="mui-card-content" style="overflow:hidden; padding:0px;">
            <img src="imgs/1.jpg" width="100%" />
        </div>
        <!--页脚，放置补充信息或支持的操作-->
        <div class="mui-card-footer">页脚</div>
    </div>
</div>
</body>
</html>
```
