## eBPF Labs

## setup

We will be using `ebpf-go` (github.com/cilium/ebpf) with [bpf2go](https://pkg.go.dev/github.com/cilium/ebpf/cmd/bpf2go) to simplify compilation and running of our ebpf prorgrams

### install dependencies

On a linux machine, install the eBPF dependencies with
````shell
sudo apt install llvm clang libbpf-dev 
````

#### macOS setup
If you are using MacOS, you will need to setup a linux VM. 

Use lima and create a VM from [this template](https://raw.githubusercontent.com/iogbole/ebpf-network-viz/refs/heads/main/ebpf-vm.yaml)

```shell
limactl start ebpf-vm.yaml
limactl shell ebpf-vm
```

Then create a new go module and add ebpf-go
```
go mod init github.com/rileywilliams/ebpf-lab
go get github.com/cilium/ebpf
```


Finally, clone the lab repo

```shell
git clone https://github.com/dorkamotorka/ebpf-hello-world.git
```


## Basic Program

reference: https://ebpf-go.dev/guides/getting-started/#ebpf-c-program


[ringbuffer.c](ringbuffer.c) shows a basic example of tracing execve syscalls. (https://github.com/cilium/ebpf/blob/main/examples/ringbuffer/ringbuffer.c)
