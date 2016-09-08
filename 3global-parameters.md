"global"的参数是进程级别且操作系统相关。  
通常只需设置一次，一旦测试正确不需要经常修改。  
有些参数可以通过命令行指定。  

如下参数可以在"global"指定:
```
* Process management and security
   - ca-base
   - chroot
   - crt-base
   - cpu-map
   - daemon
   - description
   - deviceatlas-json-file
   - deviceatlas-log-level
   - deviceatlas-separator
   - deviceatlas-properties-cookie
   - external-check
   - gid
   - group
   - log
   - log-tag
   - log-send-hostname
   - lua-load
   - nbproc
   - node
   - pidfile
   - uid
   - ulimit-n
   - user
   - stats
   - ssl-default-bind-ciphers
   - ssl-default-bind-options
   - ssl-default-server-ciphers
   - ssl-default-server-options
   - ssl-dh-param-file
   - ssl-server-verify
   - unix-bind
   - 51degrees-data-file
   - 51degrees-property-name-list
   - 51degrees-property-separator
   - 51degrees-cache-size

 * Performance tuning
   - max-spread-checks
   - maxconn
   - maxconnrate
   - maxcomprate
   - maxcompcpuusage
   - maxpipes
   - maxsessrate
   - maxsslconn
   - maxsslrate
   - maxzlibmem
   - noepoll
   - nokqueue
   - nopoll
   - nosplice
   - nogetaddrinfo
   - spread-checks
   - server-state-base
   - server-state-file
   - tune.buffers.limit
   - tune.buffers.reserve
   - tune.bufsize
   - tune.chksize
   - tune.comp.maxlevel
   - tune.http.cookielen
   - tune.http.maxhdr
   - tune.idletimer
   - tune.lua.forced-yield
   - tune.lua.maxmem
   - tune.lua.session-timeout
   - tune.lua.task-timeout
   - tune.lua.service-timeout
   - tune.maxaccept
   - tune.maxpollevents
   - tune.maxrewrite
   - tune.pattern.cache-size
   - tune.pipesize
   - tune.rcvbuf.client
   - tune.rcvbuf.server
   - tune.sndbuf.client
   - tune.sndbuf.server
   - tune.ssl.cachesize
   - tune.ssl.lifetime
   - tune.ssl.force-private-cache
   - tune.ssl.maxrecord
   - tune.ssl.default-dh-param
   - tune.ssl.ssl-ctx-cache-size
   - tune.vars.global-max-size
   - tune.vars.reqres-max-size
   - tune.vars.sess-max-size
   - tune.vars.txn-max-size
   - tune.zlib.memlevel
   - tune.zlib.windowsize

 * Debugging
   - debug
   - quiet
```
