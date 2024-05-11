# test-keys
just for testing SSH/GPG keys

test 1 at 20240511 23:01 UTC+8

# use git with proxy

eg. you have a proxy at http://127.0.0.1:7890

so you run

```bash
git config --global https.proxy http://127.0.0.1:7890
git config --global http.proxy http://127.0.0.1:7890
```

and everything should be fine
