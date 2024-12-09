
### journalctl

  Check log size:
  sudo journalctl --disk-usage

  Clear logs (keep last 2 days):
  sudo journalctl --vacuum-time=2d

  Clear logs (limit log size to 100M):
  sudo journalctl --vacuum-size=100M


