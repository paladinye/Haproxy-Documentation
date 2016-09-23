#####stick-table
```
stick-table type {ip | integer | string [len <length>] | binary [len <length>]}
            size <size> [expire <expire>] [nopurge] [peers <peersect>]
            [store <data_type>]*
```
为当前部分配置黏着表。
适用范围:

|default | frontend | listen | backend |
|:-:|:-:|:-:|:-:|
|no | yes  | yes|yes|

|Argument|Explanation|
|:-:|:-|
|ip|该类型只存储IPv4.这种格式非常紧凑(50bytes/entry),可以几乎没有开销的查找和存储，主要用于存放源IP地址|
