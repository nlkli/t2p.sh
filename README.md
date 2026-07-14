# t2p.sh

t2p - wrapper around [tun2proxy-bin](https://github.com/tun2proxy/tun2proxy): on/off/toggles a SOCKS5/HTTP tunnel via sudo in the background, without blocking the terminal. Process state is checked via pgrep each time; no PID file is used.

### Help message

```text
USAGE
  t2p [command]

COMMANDS
  on            start the proxy if not already running
  off           stop the proxy if running
  toggle        start if stopped, stop if running
  status        show current state (default)
  -e            open this script in $EDITOR
  -l [N]        show log (last N lines, or whole file)
  -h, --help    show this help

ENV
  NO_COLOR      set to disable colored output
```

### Example

```text
nlkli@air:~
> t2p                                                                   I
  Status:  stopped
  IP:      175.107.234.77
  Location: Russian Federation, RU
nlkli@air:~
> t2p on                                                                I
Starting proxy...
[ OK ] Proxy started
  PID:     59542 59544 59545
  IP:      91.81.88.133
  Location: Finland, FI
nlkli@air:~
> t2p off                                                               I
Stopping proxy (PID 59542 59544 59545)...
[ OK ] Proxy stopped
  IP:      175.107.234.77
  Location: Russian Federation, RU
nlkli@air:~
> t2p toggle                                                            I
Starting proxy...
[ OK ] Proxy started
  PID:     59765 59767 59768
  IP:      91.81.88.133
  Location: Finland, FI
```
