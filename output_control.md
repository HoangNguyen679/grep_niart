## Count matching

```
❯ grep -c '03/22 08:51:01' sample_log

5
```

## Coloring

`03/22 08:51:01` is red ??? It is normal, isn't it ?

```
❯ grep -color '03/22 08:51:01' sample_log

03/22 08:51:01 INFO   :.main: *************** RSVP Agent started ***************
03/22 08:51:01 INFO   :...locate_configFile: Specified configuration file: /u/user10/rsvpd1.conf
03/22 08:51:01 INFO   :.main: Using log level 511
03/22 08:51:01 INFO   :..settcpimage: Get TCP images rc - EDC8112I Operation not supported on socket.
03/22 08:51:01 INFO   :..settcpimage: Associate with TCP/IP image name = TCPCS
```

## Show file has matching

```
❯ grep -l '03/22 08:51:01' sample_log sample_log_second

sample_log

❯ grep -l '03/22 08:54:53' sample_log sample_log_second

sample_log
sample_log_second

❯ grep -L '03/22 08:51:01' sample_log sample_log_second

sample_log_second
```

`-L` is opposite to `-l`

## First N selected lines

```
❯ grep -m 2 '03/22 08:51:01' sample_log

03/22 08:51:01 INFO   :.main: *************** RSVP Agent started ***************
03/22 08:51:01 INFO   :...locate_configFile: Specified configuration file: /u/user10/rsvpd1.conf

```

## Only matching part of line

Useless ??? Can use `-c` instead ?

```
❯ grep -o '03/22 08:51:01' sample_log

03/22 08:51:01
03/22 08:51:01
03/22 08:51:01
03/22 08:51:01
03/22 08:51:01
```

## Immediately quit

Exit and return 0 if match found

```
❯ grep -q '03/22 08:51:01' sample_log
```