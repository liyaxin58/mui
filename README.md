# mui
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
5. 























