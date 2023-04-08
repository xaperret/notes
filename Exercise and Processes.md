### Exercise and Processes

Use `ps` what these process have in common.

```shell
➜  bash git:(master) ✗ ps
    PID TTY          TIME CMD
  14350 pts/0    00:00:00 zsh
  14976 pts/0    00:00:00 ps
```

They have the same `TTY`, they belong to the terminal. Using just `ps` show the process of the current terminal.

Use `ps -ef`, find a [[Process]] which is the child of another

```shell
xavierp+   14350   14342  0 14:45 pts/0    00:00:00 zsh
xavierp+   14342    1808  0 14:45 ?        00:00:14 /usr/libexec/gnome-terminal-server
```

Find a command to list every [[Process]] that belongs to you

```shell
➜  ~ ps -ef | grep xavierperret       
xavierp+    4600    4599  0 09:00 ?        00:00:06 i3xrocks -u /home/xavierperret/.config/regolith/i3xrocks/conf.d -d /etc/regolith/i3xrocks/conf.d
xavierp+   48553       1  0 09:28 ?        00:00:00 /opt/brave.com/brave/chrome_crashpad_handler --monitor-self --monitor-self-annotation=ptype=crashpad-handler --database=/home/xavierperret/.config/BraveSoftware/Brave-Browser/Crash Reports --metrics-dir=/home/xavierperret/.config/BraveSoftware/Brave-Browser --url=https://cr.brave.com --annotation=lsb-release=Pop!_OS 21.04 --annotation=plat=Linux --annotation=prod=Chrome_Linux --annotation=ver=94.1.30.89 --initial-client-fd=6 --shared-client-connection
xavierp+   48555       1  0 09:28 ?        00:00:00 /opt/brave.com/brave/chrome_crashpad_handler --no-periodic-tasks --monitor-self-annotation=ptype=crashpad-handler --database=/home/xavierperret/.config/BraveSoftware/Brave-Browser/Crash Reports --url=https://cr.brave.com --annotation=lsb-release=Pop!_OS 21.04 --annotation=plat=Linux --annotation=prod=Chrome_Linux --annotation=ver=94.1.30.89 --initial-client-fd=4 --shared-client-connection
xavierp+  167649  143337  0 10:39 pts/0    00:00:00 grep --color xavierperret
➜  ~ 

```
