# How to use DNSAPI

Since MailinaBox isn't yet integrated to acme.sh, you can use dns alias mode until our pull request is accpeted: 

https://github.com/Neilpang/acme.sh/wiki/DNS-alias-mode

## Use MailinaBox Custom DNS API to automatically issue cert

First you need an Administrator account to use MIAB API and the name of your mail server.

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
