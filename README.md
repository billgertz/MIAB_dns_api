# How to use DNS API

If your dns provider doesn't provide api access, you can use our dns alias mode: 

https://github.com/Neilpang/acme.sh/wiki/DNS-alias-mode

## 1. Use Mail In A Box API to automatically issue cert

First you need an Administrator account to use MIAB API and the name of your mail server.
You'll also need the curl package to be installed. wget doesn't work at the moment.

```
export $MIAB_Username="admin@yourbox.email"
export $MIAB_Password="password"
export $MIAB_Server="box.yourbox.email"
```

Ok, let's issue a cert now:
```
acme.sh --issue --dns dns_miab -d example.com -d www.example.com
```

Now, let's issue a wildcard certificate now:
```
acme.sh --issue --dns dns_miab -d \*.example.com
```

The `$MIAB_Username`, `$MIAB_Password` and `$MIAB_Server` will be saved in `~/.acme.sh/account.conf` and will be reused when needed.