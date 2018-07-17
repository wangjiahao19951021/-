一、事件代理
    1、事件代理是一种编程思想，是一个编程方案，是这样的一种方式：在网页中存在父节点内的多个子节点时
    ，这些子节点有相同的事件，按照原有的思路的话是找到每个子节点，然后给每个子节点添加事件；代理的方式是
    将事件添加在上层的父节点处，给父节点添加此事件，在父节点中能够找到原目标元素，通过判断实现分支
    功能
    事件代理的关键点：第一相同的事件，第二在父节点添加事件，第三能够区分目标元素，第四实现不同功能

作业：
有一张表格，在表格中的最后一列假设内容是“删除”，当点击带有“删除”字样的单元格时能够将本单元格所在的
整行删除掉

模拟购物车，在购物车中假设有一些商品的列表，提供每个商品的删除功能，当点击此删除功能时将此商品
移出购物车

二、Date类
    1、了解一下UTC  GMT  LT

    2、创建日期
       1）第一种格式：
          var da = Date();----此格式创建的是字符串

       2）第二种格式：创建日期对象
          a、第1格式:var da = new Date();
          b、填充时间字符串创建日期对象
             填充的字符串的格式也有三种：
             英文格式:英文的月 日,年 时:分钟:秒
             ，yyyy-MM-dd hh:mm:ss，
             yyyy/mm/dd hh:mm:ss
          c、第三种格式：
          var da = new Date(year,month[,day,hour,minute,second]);
          此格式year和month两个参数必须设置，其他可选

    3、了解Date类中的方法----getxxx和setxxx
       1）获取或者设置年份---设置或者获取4位数字的年份
          getFullYear()   setFullYear()
       2）获取或者设置月份---月份从0-11计数
          getMonth()  setMonth()
       3）获取或者设置日期
          getDate()  setDate()---setDate方法如果设置的日期超出了当前月的总天数，那么会自动
          算入下一个月

       4）获取或者设置小时
          getHours()   setHours()  0-23
       5）获取或者设置分钟
          getMinutes()  setMinutes() 0-59
       6）获取或者设置秒
          getSeconds()  setSeconds() 0-59

       7）获取或者设置毫秒
          getMiliSeconds()  setMiliSeconds()

       8）获取从1970年1月1日0时0分0秒开始至今的毫秒数
          getTime()   setTime()

       9）另一组获取和设置方法getUTCxxx()和setUTCxxx()

       10）getDay()  0-6--获取星期的编号从星期日到星期六

       11）将日期对象转换为字符串
           toxxxString()

           toString()   toUTCString()   toLocaleString()
           toDateString() +  toTimeString() = toString()
           toLocaleDateString()  + toLocaleTimeString() = toLocaleString()

           valueOf()---返回毫秒数

           显示固定的日期格式的字符串
           2017年12月1日 15时26分30秒

           2017年12月1日 15:26:30

作业：制作一个全年的万年历

三、正则表达式
    1、什么是正则表达式：是描述字符模式的一个对象
       常用于实现字符串是否符合特定格式的验证或者搜索，例如：在进行用户注册时
       通常用户名都有一个限制：假设此限制是要求所设置的用户名
       只能是字母，数字，下划线，并且长度8-16之间

    2、正则表达式的创建regular  expression
       1）第一
          var reg = new RegExp(参数1,参数2);
          参数1---是表达式模式
          参数2---是修饰符g,i,m
          两个参数均为字符串格式，如果不需要第二个参数那么直接设置空串""

          g---全局修饰符，如果没有设置g修饰符那么找到第一个匹配的结束
          i---不区分大小写，如果不设置i那么区分大小写
          m---在多行中实现匹配

       2）第二
          var reg = /模式/修饰符;
          \--作用实现转义，保留符号的原义

          \n \r \f \t \b \\ \' \"

    3、方法
       1）test() -- 用于测试
       2）exec() -- 用于捕获

       













