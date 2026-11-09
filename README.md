# t2p.sh

t2p - wrapper around [tun2proxy-bin](https://github.com/tun2proxy/tun2proxy): on/off/toggles a SOCKS5/HTTP tunnel via sudo in the background, without blocking the terminal. Process state is checked via pgrep each time; no PID file is used.

```text
Notes:
  - "sudo -b" launches the process detached in the background and returns
    control immediately - no nohup/disown/& needed.
  - No PID file. State is derived each call via `pgrep -f` on PROXY_MATCH.
    This avoids stale state if the process was killed manually.
Usage:
  ./t2p on         start proxy if not already running
  ./t2p off        stop proxy if running
  ./t2p r/restart  restart proxy if running, start it if stopped
  ./t2p t/toggle   start if stopped, stop if running
  ./t2p s/status   print current state (default)
  ./t2p -e         open this script in $EDITOR and exit
  ./t2p -l [N]     show log (last N lines, or whole file)
  ./t2p -h         show help
```
