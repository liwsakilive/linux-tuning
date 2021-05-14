# Add ulimit for nginx
```
www-data        soft    nofile          100000
www-data        hard    hard            120000
www-data        soft    nproc           100000
www-data        hard    nproc           100000

nginx soft nofile 10000
nginx hard nofile 30000

# End of file
```

# Tuning ulimit on online
```
ulimit -n 150000
```

# Add sysctl.conf
```
#
#net.ipv4.tcp_fin_timeout = 60
#net.ipv4.tcp_retries1 = 3
net.ipv4.tcp_keepalive_probes = 9
net.ipv4.tcp_keepalive_time = 7200
net.ipv4.tcp_syn_retries = 5
kernel.sem = 250 32000 100 128
kernel.shmall = 209715200
kernel.shmmax = 214748364800
kernel.shmmni = 4096
fs.file-max = 1000000
vm.swappiness = 0
vm.vfs_cache_pressure = 50
net.ipv4.tcp_fin_timeout = 3
net.core.netdev_max_backlog = 30000
net.ipv4.tcp_no_metrics_save = 1
net.ipv4.tcp_synack_retries = 2
net.ipv4.tcp_syn_retries = 2
net.ipv4.tcp_max_syn_backlog = 8192
net.core.rmem_max = 16777216
net.core.wmem_max = 16777216
net.ipv4.tcp_rmem = 4096 87380 16777216
net.ipv4.tcp_wmem = 4096 65536 16777216
net.core.somaxconn = 8192
vm.min_free_kbytes = 65536
#net.core.rmem_max = 16777216
#net.core.wmem_max = 16777216
#net.ipv4.tcp_rmem = 4096 87380 16777216
#net.ipv4.tcp_wmem = 4096 65536 16777216
#net.ipv4.tcp_no_metrics_save = 1
#net.ipv4.tcp_syncookies = 1
#net.ipv4.tcp_max_syn_backlog = 2048
#net.ipv4.tcp_synack_retries = 2
#net.ipv4.tcp_syncookies
net.ipv4.tcp_tw_reuse = 1
net.ipv4.tcp_tw_recycle = 1
net.ipv4.tcp_mem = 786432 1048576 1572864
kernel.pid_max = 65536
net.ipv6.conf.all.disable_ipv6=1
net.ipv4.tcp_syncookies = 1
net.bridge.bridge-nf-call-iptables = 0
net.ipv4.ip_local_port_range = 2000 65000
net.ipv4.tcp_window_scaling = 1
# number of packets to keep in backlog before the kernel starts dropping them
net.ipv4.tcp_max_syn_backlog = 8240000
# increase socket listen backlog
#net.core.somaxconn = 824000
net.ipv4.tcp_max_tw_buckets = 1440000
# Increase TCP buffer sizes
net.core.rmem_default = 8388608
net.core.rmem_max = 16777216
net.core.wmem_max = 16777216
net.ipv4.tcp_rmem = 4096 87380 16777216
net.ipv4.tcp_wmem = 4096 65536 16777216
net.ipv4.tcp_congestion_control = cubic
net.bridge.bridge-nf-call-iptables = 0
kernel.perf_event_max_sample_rate = 25000
net.netfilter.nf_conntrack_max = 556000
net.ipv4.tcp_congestion_control=htcp
net.ipv4.netfilter.ip_conntrack_max = 409600
kernel.printk_ratelimit = 30
kernel.printk_ratelimit_burst = 500
net.ipv4.conf.all.rp_filter = 1
net.netfilter.nf_conntrack_max = 10000000 
net.netfilter.nf_conntrack_tcp_loose = 0 
net.netfilter.nf_conntrack_tcp_timeout_established = 1800 
net.netfilter.nf_conntrack_tcp_timeout_close = 10 
net.netfilter.nf_conntrack_tcp_timeout_close_wait = 10 
net.netfilter.nf_conntrack_tcp_timeout_fin_wait = 20 
net.netfilter.nf_conntrack_tcp_timeout_last_ack = 20 
net.netfilter.nf_conntrack_tcp_timeout_syn_recv = 20 
net.netfilter.nf_conntrack_tcp_timeout_syn_sent = 20 
net.netfilter.nf_conntrack_tcp_timeout_time_wait = 10
fs.file-max=500000
```
