## How to set proxy to apt?

To do this in ubuntu we must go through this way:

1- in `/etc/apt/apt.conf.d/` make a file `proxy.conf`.
2- in `proxy.conf` add this line 
`Acquire::http::Proxy "http://username:password@proxy.server:port/";` and this for https:
`Acquire::https::Proxy "http://username:password@proxy.server:port/";`

if want to use proxy for specific repo add this line:
`Acquire::http::Proxy::external.repo.host "http://username:password@proxy.server:port/";`
