####HTTP request
首先我们看一个http request的例子：
```
  Line     Contents
  number
     1     GET /serv/login.php?lang=en&profile=2 HTTP/1.1
     2     Host: www.mydomain.com
     3     User-agent: my small browser
     4     Accept: image/jpeg, image/gif
     5     Accept: image/png
```
#####The Request line
第一行是“request line”.通常由3部分组成：
```
  - a METHOD      : GET
  - a URI         : /serv/login.php?lang=en&profile=2
  - a version tag : HTTP/1.1
```
他们被LWS分割，通常是空白符，也是可以tab或者\r,\n后跟空格/tab.  
method不能包含:,只能是字母。
这种request line的组织形式使haproxy能很好的拆分。  

URI有集中形式：
- 相对URI:  

	/serv/login.php?lang=en&profile=2
- 绝对URI: 
 
	http://192.168.0.12:8080/serv/login.php?lang=en&profile=2
- *: 
 
	适用于option方法，检测服务器状态,类似ping
- 地址加端口号:  

	192.168.0.12:80  

相对URI中，？之前的是路径，？之后的是参数，以get方法传递给相应的动态语言进行处理。
#####The request headers
第二行开始是header,其组成形式为:  
  > name:values  
一行可包含多对，比如cookie
header大小写不敏感

无论header形式如何，haproxy已经做了预处理，方便我们按照haproxy的说明直接使用。

