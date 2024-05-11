# test-keys
just for testing SSH/GPG keys

test 1 at 20240511 23:01 UTC+8

# use git with proxy

eg. you have a proxy at http://127.0.0.1:7890

so there are 4 methods for different situations

```bash
# Method 1. git http + proxy http
git config --global http.proxy "http://127.0.0.1:1080"
git config --global https.proxy "http://127.0.0.1:1080"

# Method 2. git http + proxy shocks
git config --global http.proxy "socks5://127.0.0.1:1080"
git config --global https.proxy "socks5://127.0.0.1:1080"

# to unset
git config --global --unset http.proxy
git config --global --unset https.proxy

# Method 3. git ssh + proxy http
vim ~/.ssh/config
Host github.com
HostName github.com
User git
ProxyCommand socat - PROXY:127.0.0.1:%h:%p,proxyport=1087

# Method 4. git ssh + proxy socks
vim ~/.ssh/config
Host github.com
HostName github.com
User git
ProxyCommand nc -v -x 127.0.0.1:1080 %h %p
```

and everything should be fine. Maybe you have to add quotes "" for `%h %p` stuff
