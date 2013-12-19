perl中文处理
============

* perldoc Encode
* perldoc PerlIO
* http://www.cnblogs.com/starspace/archive/2008/12/10.html
* 上面这篇文章基本上涵盖了中文处理的很大一部分，我下面做一个简单的小结。

字符串结构
----------
- 数据
- utf8 flag
  - On，string，utf8编码的字符串
  - Off，octets，即8位序列，也就是我们通常说的字节数组
- perl输入输出的时候，只有数据，而不包括utf8 flag

字符串比较（eq返回真）
-------------
- 数据相同
- utf8 flag相同

API
---
> use Encode;
> $octets = encode(ENCODING, $string [, CHECK]);
> $string = decode(ENCODING, $octets [, CHECK]);
> is_utf8(STRING [, CHECK]);
> _utf8_on(STRING);
> _utf8_off(STRING);

一般中文处理
------------
- 将输入转化为utf8编码（decode），开启utf8 flag
- 处理
- 转化为需要的编码（encode）输出

中文匹配
--------
* （头疼问题，待解决）
* 通常可直接输入中文字符匹配
