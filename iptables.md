### Просмотр правил в iptables
```
iptables -L --line-numbers -v -n
```

### Блокирование ping в iptables

```
iptables -A INPUT -p icmp -i eth0 -j DROP

# Блокирование ip-адреса и порта в iptables
iptables -A INPUT -s 123.123.123.123 -j DROP

# Чтобы заблокировать определенный порт:
iptables -A OUTPUT -p tcp --dport 123 -j DROP

# Чтобы разрешить доступ к этому порту для определенного ip-адреса:
iptables -A INPUT -s 123.123.123.123 -p tcp -m tcp --dport 123 -j ACCEPT
```

### Удаление правил из iptables

```
iptables -L --line-numbers -v -n

iptables -D INPUT 3

# Delete all rule
# iptables -F
```
