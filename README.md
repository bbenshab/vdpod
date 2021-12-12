# vdbench-pod
how I ran it
podman build -t quay.io/bbenshab/vdbench-pod:latest . --no-cache
podman push quay.io/bbenshab/centos-vdbench-pod:latest

run container for testing:
podman run -v /workload:/workload -e BLOCK_SIZES=4,64,128  -e IO_OPERATION=write,write,write -e IO_THREADS=1,1,1  -v /root/vdbench-pod:/vdbench/config -it quay.io/bbenshab/centos-vdbench-pod:latest
