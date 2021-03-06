1. jQuery对象和DOM对象的相互转换

   ```javascript
   //jQuery对象转成DOM对象
   let box = $(".div");
   console.log(box instanceof jQuery);	//true
   console.log(box[0] instanceof jQuery);	//false

   //DOM对象转成jQuery对象
   let box = document.createElement("div");
   console.log(box instanceof jQuery);	//false
   console.log($(box) instanceof jQuery);	//true
   ```

2. 基本过滤选择器

   | 选择器         | 描述                           | 示例                                                |
   | -------------- | ------------------------------ | --------------------------------------------------- |
   | :first         | 选取第一个元素                 | $("div:first")                                      |
   | :last          | 选取最后一个元素               | $("div:last")                                       |
   | :not(selector) | 去除所有给定选择器匹配的元素   | $("div:not(.myClass)")选取class不为myClass的div元素 |
   | :even          | 选取索引是偶数的所有元素       | $("div:even")                                       |
   | :odd           | 选取索引是奇数的所有元素       | $("div:odd")                                        |
   | :eq(index)     | 选取引索等于index的元素        | $("div:eq(0)")                                      |
   | :gt(index)     | 选择索引大于index的所有元素    | $("div:gt(1)")                                      |
   | :lt(index)     | 选择索引小于index的所有元素    | $("div:lt(1)")                                      |
   | :header        | 选取所有标题元素,h1,h2...      | $("div:header")                                     |
   | :animated      | 选取当前正在执行动画的所有元素 | $(":animated")                                      |
   | :focus         | 获取当前获得焦点的元素         | $(":focus")                                         |

3. 内容过滤选择器

   内容过滤器的过滤规则主要体现在它所包含的子元素或文本内容上

   | 选择器         | 描述                           | 示例                   |
   | -------------- | ------------------------------ | ---------------------- |
   | :contain(text) | 选取含有文本内容为"text"的元素 | $("div:contain('我')") |
   | :empty         | 选取空元素                     | $("div:empty")         |
   | :has(selector) | 选取含有选择器的元素的元素     | $("div:has(.myClass)") |
   | :parent        | 选取含有子元素或者文本的元素   | $("div:parent")        |

4. 属性过滤选择器

   | 选择器                       | 描述                                    | 示例                     |
   | ---------------------------- | --------------------------------------- | ------------------------ |
   | [attribute]                  | 拥有此属性的元素                        | $("div[id]")             |
   | [attribute=value]            | 所选属性为value的元素                   | $("div[name=test]")      |
   | [attribute!=value]           | 所选属性不为value的元素                 | $("div[name!=test]")     |
   | [attribute^=value]           | 所选属性的值以value开头的元素           | $("div[title^=test]")    |
   | [attribute$=value]           | 所选属性的值以value结尾的元素           | $("div[title\$=test]")   |
   | [attribute*=value]           | 所选属性的值含有value的元素             | $("div[title*=test]")    |
   | [attribute\|=value]          | 所选元素已value为前缀的元素             | $("div[title\|=test]")   |
   | [attribute~=value]           | 所选属性用空格分隔的值中包含value的元素 | $("div[title~=test]")    |
   | \[attribute1][attribute2]... | 复合属性                                | $("div\[id][name=test]") |

5. 表单对象属性过滤选取器

   - :enabled 选取所有可用的元素
   - :disabled 选取不可用元素
   - :checked 选取所有被选中的元素（单选框，复选框
   - :selected 选取所有被选中的选项元素（下拉框

6. 表单选择器

   | 选择器    | 描述                                        |
   | --------- | ------------------------------------------- |
   | :input    | 选取所有input，textarea，select，button元素 |
   | :text     | 选取所有的单行文本框                        |
   | :password | 选取所有密码框                              |
   | :checkbox | 选取所有多选框                              |
   | :submit   | 选取所有提交按钮                            |
   | :image    | 选取所有图像按钮                            |
   | :reset    | 选取所有重置按钮                            |
   | :button   | 选取所有的按钮                              |
   | :file     | 选取所有的上传域                            |
   | :hidden   | 选取所有不可见元素                          |

7. 选择器中含有特殊字符

   选择器中含有 . # ( [ 记得转义

8. filter 筛选元素

9. 某节点remove方法删除后，该节点所包含的所有后代节点将同时删除

10. detach也是删除节点，不过与remove不同的是，所有绑定的事件和附加的数据都会被保留下来

11. empty方法为清空该元素里的所有内容，以及子代

12. clone方法，复制节点，clone方法中传递一个参数true，它的含义是复制元素的同时复制元素中的绑定事件

13. replaceWith替换元素方法，如果在替换之前，已经为元素绑定事件，替换后原先绑定的事件将会与被替换的元素一起消失，需要在新的元素上重新绑定事件

14. 包裹节点

    如果要将某个结点用其他标记包裹起来，jQuery提供了相应的方法即swap

15. 属性操作

    用attr方法来获取和设置元素属性，removeAtrr方法来删除元素属性

16. toggle(方法——切换元素的可见状态。

17. 设置和获取文本的HTML，文本和值

    - html方法——innerHTML

    - text方法——innerText

    - val方法——value

      个人感觉是value是表单元素，获取值

18. children方法只考虑直接子元素而不考虑其他后代元素

19. 同级元素操作

    - next：该方法用于取得匹配元素后面紧邻的同辈元素
    - prev：该方法用于取得匹配元素前面紧邻的同辈元素
    - siblings：该方法用于取得匹配元素前后所有的同辈元素

20. parent，parents，closest的区别

    - parent：返回直接父节点
    - parents：返回所有父节点
    - closest：和parents相似但是只返回第一个节点

21. 对于透明度的设置，可以直接使用opacity，jQuery已经做好了兼容性问题

22. 在CSS-DOM中关于元素定位的常用方法：

    - offset：获取元素在当前视窗的相对偏移
    - position：获取绝对定位相对于定位元素的祖先的距离
    - scrolltop：获取滚动条顶端的距离

23. hover方法

    hover(enter,leave)

24. preventDefault方法阻止默认行为

25. 事件对象的属性

    - event.type
    - event.preventDefault
    - event.stopPropagation 阻止事件冒泡
    - event.target
    - event.which 判断鼠标按键或者键盘按键
    - event.metaKey 获取Ctrl
    - event.pageX和event.pageY

26. one——为元素绑定处理函数，当处理触发一次之后，立即被删除

    ```javascript
    $(".botton").one("click",()=>console.log("1"));
    ```

27. 模拟事件——trigger

28. 添加事件命名空间，便于管理

    ```javascript
    $(".botton").bind("click.plugin",function () {
       console.log(1);
        $(".botton").unbind(".plugin");	//移除plugin命名空间下的事件
    });
    ```

29. trigger("click!")后面的感叹号的作用是匹配所有不包含在命名的click方法

30. 自定义动画方法

    ```javascript
    $(this).animate(params,speed,callback);
    //params:一个包含样式属性以及值的映射
    ```

31. 累加，累减动画

    ```javascript
    $(this).animate({left:"+=50px"},300);
    ```

32. 多重动画

    ```javascript
    //同时执行多个动画
    $(this).animate({left:"+=50px",height:"+=20px"},300);
    //按顺序执行多个动画
    $(this).animate({left:"+=50px"},300)
    	  .animate({height:"+=20px"},300)；
    ```

33. 判断元素是否处于动画状态

    ```javascript
    $(".test").is(":animated");
    ```

34. 动画队列

    - 一组元素上的动画效果
      - 当一个animate方法中应用多个属性时，动画是同时发生的
      - 当以链式的写法应用动画方法时，动画是按照顺序发生的
    - 多组元素的动画效果
      - 默认情况下，动画是同时发生的
      - 当以回调的形式应用动画方式时，动画是按照回调顺序发生的

35. 表单提交时可以根据错误提示的class数量判断可不可以提交

36. 可以给表单元素绑定keyup事件和focus事件，实现即时提醒

37. end方法

    ```javascript
    $(this).addClass("selected")
        .siblings().removeClass("selected")
        .end()
        .find(":radio").attr("checked",true);
    ```

    当前对象是\$(this)在进行addClass("selected")操作之后，对象并未发生变化，但执行了.siblings().removeClass("selected")之后，对象已经变成了$(this).siblings()了，后面的操作都是针对$(this).siblings()的，如果需要返回到$(this)对象就可以使用end()方法

38. ajax方法常用参数

    - url
    - type
    - data
    - dataType——预期服务器返回的数据类型
    - beforeSend——发送请求前可以修改XMLHttpRequest对象的函数，例如添加自定义的HTTP头
    - complete——请求完成调用的回调函数，成功失败均可以
    - success——有两个参数(data,textStatus)
    - error——三个参数依次是XMLHttpRequest对象，错误信息，捕获的错误对象
    - global——是否触发全局ajax事件，默认true

39. ajax方法中data是字符串方式时，需要注意对字符串的编码，如果不希望编码带来麻烦，可以使用serialize方法

40. 直接提交表单元素

    ```javascript
    $("#form1").serialize()
    ```

41. $.param方法：serialize方法的核心，用来对数组和对象序列化

    ```javascript
    var obj = {a:1,b:2,c:3};
    var k = $.param(obj);
    alert(k);//a=1&b=2&c=3
    ```

42. ajax的全局事件

43. 定义视口

44. data-属性是H5新推出的很有趣的一个特性，它可以让开发人员添加任意属性到html标签中，只要添加的属性名有"data-"前缀

45. jQuery性能优化

    - 使用最新版jQuery

    - 使用合适的选择器

      - 尽量使用id选择器，如果找不到再调用find方法
      - 标签选择器是第二选择
      - 类选择器有选择的使用它
      - 利用属性选择器定位DOM元素性能不是非常理想
      - 伪选择器同上
      - 尽量给选择器指定上下文

    - 缓存对象

      频繁使用的DOM对象可以定义一个变量将其缓存

    - 避免在循环中操作DOM

    - 数组方式使用jQuery对象，而不是each

    - 事件委托

    - join拼接字符串

    - 合理利用H5的Data属性

      jQuery的data方法

      ```javascript
      //<div id="d1" data-role="page"></div>
      $("#d1").data("role")//page
      ```

    - 尽量使用原生js

    - 压缩js

    ​