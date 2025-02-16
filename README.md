# Some custom for Falco
- Upgrade command for falco side kick if install falco with Helm:
```sh
helm upgrade falco falcosecurity/falco -n falco -f falcosidekick.yaml
```

- Add custom rule:
```sh
helm upgrade falco falcosecurity/falco -n falco --set-file customRulesFile=custom-rules.yaml
```

- Uninstall: `helm uninstall -n falco falco`

# Multiple telegram output configurations
```
# Telegram output configurations
telegram:
  - chatid: "123456789"
    token: "your-telegram-bot-token"
    minimumpriority: "debug"
    endpoint: "https://api.telegram.org"
  - chatid: "987654321"
    token: "your-telegram-bot-token"
    minimumpriority: "warning"
    endpoint: "https://api.telegram.org"
```



# Ref:
- https://github.com/falcosecurity/falcosidekick/blob/master/docs/outputs/telegram.md