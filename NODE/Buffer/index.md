> 数据都是以二进制形式来表现的，所以会出现不精准的情况
+ 一个字节8位，每个字节最大是255

+ 小数转二进制
  + 10进制中的0.5在2进制中是多少 10 => 0.5   2 => 0.1
  + 10进制中的0.5 就是2进制中的0.1  乘2取整法可以将一个小数转成2进制

+ 在服务端，我们需要一个东西可以来标识内存，但是不能是字符串，因为字符串无法标识图片
+ node中用Buffer来标识内存的数据，他把内容转换成16进制来显示
+ 16进制 0123456789abcdef  0x 16进制   0b 2进制 0o 8进制

+ node中buffer和字符串任意转换 （可能会出现乱码）
+ 编码规范
  + ASCII 最多127个 
  + GBK/GB18030
  + UTF-8
+ 单字节，一个字母，符号都是一个字节
+ 中国为了能标识自己(GB2312/GB18030/GBK) 对于文字来说，由两个字节组成
+ unicode 希望统一所有编码，可变字节长度，未统一成功
+ utf组织解决了这个问题，utf-8是unicode的实现方式之一 (utf 编码，一个汉字3个字节组成)
+ 全部统一成utf-8 node不支持gbk，只支持utf-8


>  Buffer 代表的是内存，内存时一段"固定空间"，产生的内存是固定大小，不能随意添加
+ 扩容概念，需要动态创建一个新的内容，把内容迁移过去
+ alloc 
+ from
+ slice 
+ copy 原型上的方法，可以将buffer的数据拷贝到另一个buffer上
+ concat 静态方法 
  + 第一个参数是需要合并的buffer数组
  + 第二个参数指定长度
+ indexOf
+ isBuffer



+ 无论是2进制还是16进制他们表现的东西都是一样的
+ base64编码 没有加密功能，所有人都知道这个规范
  + base64 可以放到任何路径的链接里
  + 可以减少请求的发送
  + 文件大小变大
  + base64转化完毕之后会比文件大1/3