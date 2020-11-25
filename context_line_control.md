- __Context lines__ are _non-matching lines_ that are near a matching line.
- grep never outputs any given line _more than once_.

## After context

```
❯ grep -A 2 '03/22 08:53:52' sample_log

03/22 08:53:52 TRACE  :.....rsvp_event: received event from RAW-IP on interface 9.67.116.98
03/22 08:53:52 TRACE  :......rsvp_explode_packet: v=1,flg=0,type=2,cksm=54875,ttl=255,rsv=0,len=84
03/22 08:53:52 TRACE  :.......rsvp_parse_objects: STYLE is WF
03/22 08:53:52 INFO   :.......rsvp_parse_objects: obj RSVP_HOP hop=9.67.116.99, lih=0
03/22 08:53:52 TRACE  :......rsvp_event_mapSession: Session=9.67.116.99:1047:6 exists
03/22 08:53:52 INFO   :.......rsvp_flow_stateMachine: state RESVED, event RESV
03/22 08:53:52 TRACE  :........flow_timer_stop: Stop T4
03/22 08:53:52 TRACE  :........flow_timer_start: Start T4
03/22 08:53:52 TRACE  :.......rsvp_flow_stateMachine: reentering state RESVED
03/22 08:53:53 EVENT  :..mailslot_sitter: process received signal SIGALRM
03/22 08:53:53 TRACE  :.....event_timerT1_expire: T1 expired
```

```
❯ grep -A 2 '03/22 08:53:52 TRACE' sample_log

03/22 08:53:52 TRACE  :.....rsvp_event: received event from RAW-IP on interface 9.67.116.98
03/22 08:53:52 TRACE  :......rsvp_explode_packet: v=1,flg=0,type=2,cksm=54875,ttl=255,rsv=0,len=84
03/22 08:53:52 TRACE  :.......rsvp_parse_objects: STYLE is WF
03/22 08:53:52 INFO   :.......rsvp_parse_objects: obj RSVP_HOP hop=9.67.116.99, lih=0
03/22 08:53:52 TRACE  :......rsvp_event_mapSession: Session=9.67.116.99:1047:6 exists
03/22 08:53:52 INFO   :.......rsvp_flow_stateMachine: state RESVED, event RESV
03/22 08:53:52 TRACE  :........flow_timer_stop: Stop T4
03/22 08:53:52 TRACE  :........flow_timer_start: Start T4
03/22 08:53:52 TRACE  :.......rsvp_flow_stateMachine: reentering state RESVED
03/22 08:53:53 EVENT  :..mailslot_sitter: process received signal SIGALRM
03/22 08:53:53 TRACE  :.....event_timerT1_expire: T1 expired
```

## Before Context

`-A num` → `-B num`

## Context (Before + After)

`-A num` → `-C num`
