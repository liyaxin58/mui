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






















