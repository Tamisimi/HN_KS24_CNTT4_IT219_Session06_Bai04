# Bài 4 — nohup và kill

## Script

File: `loop-monitor.sh` — ghi thời gian vào `/tmp/monitor.log` mỗi 5 giây.

```bash
chmod +x loop-monitor.sh
nohup ./loop-monitor.sh > /dev/null 2>&1 &
```

## PID

```bash
pgrep -f loop-monitor.sh
# ví dụ: 12345
```

## Log

```bash
tail -n 10 /tmp/monitor.log
```

Mẫu:

```text
System time: Tue Oct  6 21:50:01 UTC 2026
System time: Tue Oct  6 21:50:06 UTC 2026
```

## Tắt tiến trình

```bash
kill -15 12345
# nếu còn: kill -9 12345
ps aux | grep loop-monitor.sh
```

Sau `kill -15`, tiến trình không còn trong `ps`.
