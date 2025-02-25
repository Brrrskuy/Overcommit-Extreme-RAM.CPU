# Overcommit Extreme RAM CPU
- Buy VPS di : [t.me/skuycloud](t.me/skuycloud)
- Trakteer buat buy Kopi : https://trakteer.id/brrrskuy/tip `<---`

`Izinkan Overcommit Memory`
```
cat /proc/sys/vm/overcommit_memory
```
`Jika 0 tambahkan hasil = 1`
```
echo 1 > /proc/sys/vm/overcommit_memory
```
`add Permanent overcommit`
```
echo "vm.overcommit_memory=1" >> /etc/sysctl.conf
sysctl -p
```
`Strict mode if overcommit error`
```
echo 2 > /proc/sys/vm/overcommit_memory
echo 150 > /proc/sys/vm/overcommit_ratio
```
`Overswap Extreme Memory`
```
fallocate -l 32G /swapfile2
chmod 600 /swapfile2
mkswap /swapfile2
swapon /swapfile2
```
`Overcommit CPU, RAM, dan Swap test`
```
apt install cpulimit stress -y
```
`Run stress test`
```
stress --cpu 16 --io 6 --vm 6 --vm-bytes 4G --timeout 180
```
