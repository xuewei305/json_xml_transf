# json_xml_transf<br/>
  使用cjson库写的一个json和xml互相转化的例子
##使用说明
=========
  直接复制其中的cJson.h cJson.cpp Json.h Json.cpp，调用里面的json2xml 和 xml2json来进行相互转化
##暂时存在的问题
=========
  这个库暂时没有考虑某些情况：
   1. xml中存在标签的问题
   2. "<label>123<lab>123</lab></label>" 这种情况下该如何解析成json
##更新日志
=========
  ###20170424：
  =========
  在网上找了份代码，重写了它里面的xml转json部分
  ###20170505：
  =========
  重写了所有代码，修复了一个bug。
  在将其放到实际项目中进行运行的时候发现如果在xml标签中"<>"作为值而不是标签的时候，解析会出现错误
  例如：里面如果存在这样的项<banner>"HTTP/1.1 200\ncontent-length:81\naccept-ranges:bytes\nexpires:Tue, 23 Feb 2016 13:37:17 GMT\nserver:Apache\nlast-modified:Tue, 12 Jan 2010 13:48:00 GMT\nconnection:Close\netag:51-47cf7e6ee8400\ncache-control:max-age=86400\ndate:Mon, 22 Feb 2016 13:37:17 GMT\ncontent-type:text/html\n\n\n<html>\n<meta http-equiv=refresh content=0;url=http://www.baidu.com/>\n</html>\n\"</banner>
  它会将<html>作为一个新的xml项，而不是作为banner中的字符串
