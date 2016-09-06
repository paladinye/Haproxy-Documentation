####HTTP Response
形式与http request 相同，可以根据状态码，分析response，可参考:RFC2616  
#####The Response line
haproxy本身也会产生一些状态码，如200,301,400等
#####The response headers
与request headers 一样，haproxy用同样的解析方法处理request/response header.
