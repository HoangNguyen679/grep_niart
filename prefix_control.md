## Byte offset

```
❯ grep -b '03/22 08:51:01' sample_log

0:03/22 08:51:01 INFO   :.main: *************** RSVP Agent started ***************
81:03/22 08:51:01 INFO   :...locate_configFile: Specified configuration file: /u/user10/rsvpd1.conf
178:03/22 08:51:01 INFO   :.main: Using log level 511
228:03/22 08:51:01 INFO   :..settcpimage: Get TCP images rc - EDC8112I Operation not supported on socket.
330:03/22 08:51:01 INFO   :..settcpimage: Associate with TCP/IP image name = TCPCS

❯ grep -b -o '03/22 08:51:01' sample_log

0:03/22 08:51:01
81:03/22 08:51:01
178:03/22 08:51:01
228:03/22 08:51:01
330:03/22 08:51:01
```

Oh, so here I can see some benefit of `-o` :>

## Filename

If has more than one file, don't show the filename.
Default: show file name. Can specify through `-H`

```
❯ grep -h '03/22 08:54:53' sample_log sample_log_second

03/22 08:54:53 EVENT  :..mailslot_sitter: process received signal SIGTERM
03/22 08:54:53 INFO   :...check_signals: received TERM signal
03/22 08:54:53 INFO   :......term_policyAPI: UnRegisterFromPolicyAPI:  Entering
03/22 08:54:53 INFO   :......term_policyAPI: ReadBuffer:  Entering
03/22 08:54:53 INFO   :......term_policyAPI: ReadBuffer:  Exiting
03/22 08:54:53 INFO   :......term_policyAPI: UnRegisterFromPolicyAPI:  Result = 0
03/22 08:54:53 INFO   :......term_policyAPI: UnRegisterFromPolicyAPI:  Exiting
03/22 08:54:53 INFO   :......term_policyAPI: APITerminate:  Entering
03/22 08:54:53 INFO   :......term_policyAPI: APITerminate:  Exiting
03/22 08:54:53 INFO   :......term_policyAPI: Policy API terminated
03/22 08:54:53 INFO   :......dreg_process: deregistering process with the system
03/22 08:54:53 INFO   :......dreg_process: attempt to dereg (ifaeddrg_byaddr)
03/22 08:54:53 INFO   :......dreg_process: rc from ifaeddrg_byaddr  rc =0
03/22 08:54:53 INFO   :.....terminator: process terminated with exit code 0
03/22 08:54:53 INFO   :.....terminator: process terminated with exit code 0
```

## Line number

```
❯ grep -n '03/22 08:51:02' sample_log

6:03/22 08:51:02 INFO   :..reg_process: registering process with the system
7:03/22 08:51:02 INFO   :..reg_process: attempt OS/390 registration
8:03/22 08:51:02 INFO   :..reg_process: return from registration rc=0
```

## Output a zero byte

Instead of new line at the end of file name, we have zero-byte.
I still don't understand what circumstance it is used for.

```
❯ grep -l -Z '03/22 08:54:53' sample_log sample_log_second

sample_log
sample_log_second
```

