## Delimit the option list

So, `--` make `-filename` become valid ?

```
❯ grep '03/22 08:51:01' sample_log -sample_log

grep: Invalid argument

❯ grep '03/22 08:51:01' -- sample_log -sample_log

sample_log:03/22 08:51:01 INFO   :.main: *************** RSVP Agent started ***************
sample_log:03/22 08:51:01 INFO   :...locate_configFile: Specified configuration file: /u/user10/rsvpd1.conf
sample_log:03/22 08:51:01 INFO   :.main: Using log level 511
sample_log:03/22 08:51:01 INFO   :..settcpimage: Get TCP images rc - EDC8112I Operation not supported on socket.
sample_log:03/22 08:51:01 INFO   :..settcpimage: Associate with TCP/IP image name = TCPCS
-sample_log:03/22 08:51:01 INFO   :.main: *************** RSVP Agent started ***************
-sample_log:03/22 08:51:01 INFO   :...locate_configFile: Specified configuration file: /u/user10/rsvpd1.conf
-sample_log:03/22 08:51:01 INFO   :.main: Using log level 511
-sample_log:03/22 08:51:01 INFO   :..settcpimage: Get TCP images rc - EDC8112I Operation not supported on socket.
-sample_log:03/22 08:51:01 INFO   :..settcpimage: Associate with TCP/IP image name = TCPCS
```
