**cgexec**  is a small program that executes a command in a cgroup. This allows limits to be set on I/O, Memory and CPU usage in a much more fine fine grained way compared with the ***nice*** and ***ionice*** commands.

It requires Linux **Control Groups v2** to be enabled and mounted on /sys/fs/cgroup

Usage: **-i** *<io.weight>* **-c** *<cpu.weight>* **-m** *<memory.high>* **-M** *<memory.max>* **-g** *<group>* **<cmd>**

option | value
------------ | -------------
cpu.weight   | 0-10000, default 50.
io.weight    | 0-10000, default 50.
memory.high  | 0-max, default 'max'. Soft limit.
memory.max   | 0-max, default 'max'. Hard limit.
group        | existing cgroup to attach to (not implemented). Default 'cmd.xxxx' temportary group.
cmd          | command to execute.

Information about Linux CGroups can be found in the Kernel documentation: https://www.kernel.org/doc/Documentation/cgroup-v2.txt
