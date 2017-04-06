
# JQuery

    $(this).hide() - 隐藏当前元素
    $("p").hide() - 隐藏所有 <p> 元素
    $("p.test").hide() - 隐藏所有 class="test" 的 <p> 元素
    $("#test").hide() - 隐藏所有 id="test" 的元素

## 语法
- 在完全加载（就绪）之后运行 jQuery 代码。
   $(document).ready(function(){
   // 开始写 jQuery 代码...
  });
## 选择器
##### 元素选择器
   $("p")    在页面中选取所有p元素
##### #id选择器 
   $("#test")  通过 id 选取元素
##### .class选择器
   $(".test")  通过类查找元素

## 事件  
        鼠标事件               键盘事件             表单事件 	         文档/窗口事件
        click 	            keypress            submit 	               load
        dblclick双击 	    keydown键按下      	change                 resize
        mouseenter  	    keyup键抬起 	        focus 获取焦点          scroll
        mouseleave 	  	                        blur 失去焦点	       unload
        mousedown鼠标按下
        mouseup鼠标抬起
        hover 光标悬停
 -  $("p").click(function(){
      鼠标点击p元素后执行的代码!!
   });
   
 -  $("#p1").mouseenter(function(){
     alert("p1");  鼠标移入p1时，桌面弹出p1
   });
   
# jquery效果

> $(selector).show(speed,callback);
  可选的 speed 参数规定隐藏/显示的速度，可以取以下值："slow"、"fast" 或毫秒。 
  可选的 callback 参数是隐藏或显示完成后所执行的函数名称。
  
## 显示和隐藏       (可以指定时间)
  $("#hide").click(function(){
        $("p").hide(); 隐藏
  });
  
  $("#show").click(function(){
          $("p").show();  显示
  });
  $("button").click(function(){
    $("p").toggle();  切换
  });
  > toggle() 方法来切换 hide() 和 show() 方法。

    
## 淡入淡出        (可以指定时间)

  jQuery fadeIn(speed,callback)淡入
  jQuery fadeOut(speed,callback)淡出
  jQuery fadeToggle(speed,callback)切换淡入和淡出
  jQuery fadeTo(speed,opacity,callback)渐变为给定的不透明度（值介于 0 与 1 之间）。
  
- 实例 

        $("button").click(function(){
          $("#div1").fadeIn();
          $("#div2").fadeIn("slow");
          $("#div3").fadeIn(3000);
       });

## 滑动       (可以指定时间)

    slideDown(speed,callback)向下滑
    slideUp(speed,callback)向上
    slideToggle(speed,callback)切换上下
## 动画
$(selector).animate({params},speed,callback);
必需的 params 参数定义形成动画的 CSS 属性。
可选的 speed 参数规定效果的时长。它可以取以下值："slow"、"fast" 或毫秒。
可选的 callback 参数是动画完成后所执行的函数名称。

##### jQuery animate() - 操作多个属性

实例

    $("button").click(function(){
        $("div").animate({
         left:'250px',
         opacity:'0.5',
         height:'150px',
         width:'150px'
         });
     });
## 停止动画
 $(selector).stop(stopAll,goToEnd);
可选的 stopAll 参数规定是否应该清除动画队列。默认是 false，即仅停止活动的动画，允许任何排入队列的动画向后执行。
可选的 goToEnd 参数规定是否立即完成当前动画。默认是 false。
## callback
- Callback 函数在当前动画 100% 完成之后执行。

        $("button").click(function(){
           $("p").hide("slow",function(){
             alert("The paragraph is now hidden");
          });
       });
## Chaining 链式写法
    
    $("#p1").css("color","red").slideUp(2000).slideDown(2000);

## jq的捕获
### 获得内容 - text()、html() 以及 val()
    text() - 设置或返回所选元素的文本内容
    html() - 设置或返回所选元素的内容（包括 HTML 标记）
    val() - 设置或返回表单字段的值
### 获取属性 - attr()
## 设置内容和属性
$("#btn1").click(function(){

    $("#test1").text("Hello world!");
});

$("#btn2").click(function(){

    $("#test2").html("\<b\>Hello world!\</b\>");
});

$("#btn3").click(function(){

    $("#test3").val("RUNOOB");    
});
## jQuery attr() 方法也用于设置/改变属性值。
$("button").click(function(){

    $("#runoob").attr({
        "href" : "http://www.runoob.com/jquery",
        "title" : "jQuery 教程"
    });
})
## 添加新的 HTML 内容  
      append() - 在被选元素的结尾插入内容
      prepend() - 在被选元素的开头插入内容
      after() - 在被选元素之后插入内容
      before() - 在被选元素之前插入内容
- 在下面的例子中，我们创建若干个新元素。这些元素可以通过 text/HTML、jQuery 或者 JavaScript/DOM 来创建。然后我们通过 append() 方法把这些新元素追加到文本中（对 prepend() 同样有效）：
实例

    function appendText()
    
        {
             var txt1="\<p\>文本。\</p\>";              // 使用 HTML 标签创建文本   
             var txt2=$("\<p\>\</p\>").text("文本。");  // 使用 jQuery 创建文本
            var txt3=document.createElement("p");
            txt3.innerHTML="文本。";               // 使用 DOM 创建文本 text with DOM
            $("body").append(txt1,txt2,txt3);        // 追加新元素
       }


## 删除元素/内容
  
  如需删除元素和内容，一般可使用以下两个 jQuery 方法：
  
      remove() - 删除被选元素（及其子元素） 自己也被移除
      empty() - 从被选元素中删除子元素  不删除自己
      $("p").remove(".abc");    过滤删除  只删除类名为abc的p元素
##jQuery 操作 CSS
  
  jQuery 拥有若干进行 CSS 操作的方法。我们将学习下面这些：
  
      addClass() - 向被选元素添加一个或多个类
      removeClass() - 从被选元素删除一个或多个类
      toggleClass() - 对被选元素进行添加/删除类的切换操作
      css() - 设置或返回样式属性
## jQuery css() 方法
  
  css() 方法设置或返回被选元素的一个或多个样式属性。
  
  $("p").css({"background-color":"yellow","font-size":"200%"}); 
  
## 尺寸
   http://www.runoob.com/jquery/jquery-dimensions.html
---------------------------------------------------------------------------
 
## 遍历祖先


向上遍历 DOM 树


这些 jQuery 方法很有用，它们用于向上遍历 DOM 树：

    parent() 方法返回被选元素的直接父元素。
    parents()方法返回被选元素的所有祖先元素,直到文档的根元素 (<html>)。
    parentsUntil()方法返回介于两个给定元素之间的所有祖先元素

实例

    $(document).ready(function(){

返回介于 <span\> 与 <div\> 元素之间的所有祖先元素：

    $("span").parentsUntil("div");

    }); 
## 向下遍历 DOM 树
  
  下面是两个用于向下遍历 DOM 树的 jQuery 方法：
  
      children()方法返回被选元素的所有直接子元素。也可以使用可选参数来过滤对子元素的搜索
      find()方法返回被选元素的后代元素，一路向下直到最后一个后代。
## 有许多有用的方法让我们在 DOM 树进行水平遍历：
  
      siblings()方法返回被选元素的所有兄弟元素。可选参数过滤
      next()返回被选元素的下一个弟弟元素。
      nextAll()返回被选元素的下面所有的弟弟元素。
      nextUntil()返回介于两个给定参数之间的所有弟弟元素。
      prev()
      prevAll()
      prevUntil()
## 过滤
      first()方法返回被选元素的首个元素。
      last() 方法返回被选元素的最后一个元素。
      eq() 方法返回被选元素中带有指定索引号的元素。
      filter() 方法允许您规定一个标准。不匹配这个标准的元素会被从集合中删除，匹配的元素会被返回。
      not() 方法返回不匹配标准的所有元素。  not方法与 filter() 相反。
      
      
       
