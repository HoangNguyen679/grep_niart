# Basic command

## Single pattern

```
❯ grep '03/22 08:51:01' sample_log

03/22 08:51:01 INFO   :.main: *************** RSVP Agent started ***************
03/22 08:51:01 INFO   :...locate_configFile: Specified configuration file: /u/user10/rsvpd1.conf
03/22 08:51:01 INFO   :.main: Using log level 511
03/22 08:51:01 INFO   :..settcpimage: Get TCP images rc - EDC8112I Operation not supported on socket.
03/22 08:51:01 INFO   :..settcpimage: Associate with TCP/IP image name = TCPCS
```

## Multiple patterns

All of three ways are equal.

```
❯ grep -e '03/22 08:51:01' -e '03/22 08:51:02' sample_log
❯ grep -e '03/22 08:51:01\|03/22 08:51:02' sample_log
❯ grep -E '03/22 08:51:01|03/22 08:51:02' sample_log
```

Result

```
03/22 08:51:01 INFO   :.main: *************** RSVP Agent started ***************
03/22 08:51:01 INFO   :...locate_configFile: Specified configuration file: /u/user10/rsvpd1.conf
03/22 08:51:01 INFO   :.main: Using log level 511
03/22 08:51:01 INFO   :..settcpimage: Get TCP images rc - EDC8112I Operation not supported on socket.
03/22 08:51:01 INFO   :..settcpimage: Associate with TCP/IP image name = TCPCS
03/22 08:51:02 INFO   :..reg_process: registering process with the system
03/22 08:51:02 INFO   :..reg_process: attempt OS/390 registration
03/22 08:51:02 INFO   :..reg_process: return from registration rc=0
```

## Ignore case

```
❯ grep -i 'specified' sample_log

03/22 08:51:01 INFO   :...locate_configFile: Specified configuration file: /u/user10/rsvpd1.conf

```

## Invert matching

```
❯ grep -v '03/22 08:51:01' sample_log

03/22 08:51:02 INFO   :..reg_process: registering process with the system
03/22 08:51:02 INFO   :..reg_process: attempt OS/390 registration
03/22 08:51:02 INFO   :..reg_process: return from registration rc=0
03/22 08:51:06 TRACE  :...read_physical_netif: Home list entries returned = 7
...
```

## Word Regex

Exactly word match.

```
❯ grep -w 'Agent' sample_log

03/22 08:51:01 INFO   :.main: *************** RSVP Agent started ***************

❯ grep -w 'gent' sample_log

❯ grep  'gent' sample_log
03/22 08:51:01 INFO   :.main: *************** RSVP Agent started ***************
```

## Line regex

Exactly line match.

```
❯ grep -x 'Agent' sample_log
```