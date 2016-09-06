haproxy 与其他语言一样引入了逃脱和注释。  
配置文件支持三种类型：\,'',""。  
可以使用他们来进行相关的拼接。  
如：
```
# those are equivalents:
log-format %{+Q}o\ %t\ %s\ %{-Q}r
log-format "%{+Q}o %t %s %{-Q}r"
log-format '%{+Q}o %t %s %{-Q}r'
log-format "%{+Q}o %t"' %s %{-Q}r'
log-format "%{+Q}o %t"' %s'\ %{-Q}r

# those are equivalents:
reqrep "^([^\ :]*)\ /static/(.*)"     \1\ /\2
reqrep "^([^ :]*)\ /static/(.*)"     '\1 /\2'
reqrep "^([^ :]*)\ /static/(.*)"     "\1 /\2"
reqrep "^([^ :]*)\ /static/(.*)"     "\1\ /\2"
```
