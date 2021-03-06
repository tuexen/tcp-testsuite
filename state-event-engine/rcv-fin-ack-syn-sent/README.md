# Handling of TCP Segments with the FIN-ACK-bits Set in the SYN-SENT State

## Description
This set of tests focuses on the handling of FIN-ACK-segments in the `SYN-SENT` state.

[RFC 0793](https://tools.ietf.org/html/rfc0793) requires FIN-ACK-segments to be
ignored if SND.UNA =< SEG.ACK =< SND.NXT holds and triggering the sending of
a RST segment with SEG.SEQ = SEQ.ACK otherwise.

Please note that the reception of an acceptable ACK does not stop the retransmit
timer for the SYN-segment.

## Status

| Name                                                                                                                                                                                                                                                                                       | Result FreeBSD 11.0 | Result FreeBSD Head |
|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------:|:-------------------:|
|[rcv-fin-ack-without-data-syn-sent-ack-outside-left-ipv4](rcv-fin-ack-without-data-syn-sent-ack-outside-left-ipv4.pkt "Ensure that the reception of a TCP FIN-ACK with SEG.ACK=SND.NXT-1 in the SYN-SENT state triggers the sending of a TCP RST and does not affect the TCP connection")   | Unknown             | Passed              |
|[rcv-fin-ack-without-data-syn-sent-ack-outside-left-ipv6](rcv-fin-ack-without-data-syn-sent-ack-outside-left-ipv6.pkt "Ensure that the reception of a TCP FIN-ACK with SEG.ACK=SND.NXT-1 in the SYN-SENT state triggers the sending of a TCP RST and does not affect the TCP connection")   | Unknown             | Passed              |
|[rcv-fin-ack-without-data-syn-sent-ack-left-edge-ipv4](rcv-fin-ack-without-data-syn-sent-ack-left-edge-ipv4.pkt "Ensure that the reception of a TCP FIN-ACK with SEG.ACK=SND.NXT in the SYN-SENT state does not affect the TCP connection")                                                 | Unknown             | Passed              |
|[rcv-fin-ack-without-data-syn-sent-ack-left-edge-ipv6](rcv-fin-ack-without-data-syn-sent-ack-left-edge-ipv6.pkt "Ensure that the reception of a TCP FIN-ACK with SEG.ACK=SND.NXT in the SYN-SENT state does not affect the TCP connection")                                                 | Unknown             | Passed              |
|[rcv-fin-ack-without-data-syn-sent-ack-outside-right-ipv4](rcv-fin-ack-without-data-syn-sent-ack-outside-right-ipv4.pkt "Ensure that the reception of a TCP FIN-ACK with SEG.ACK=SND.NXT+1 in the SYN-SENT state triggers the sending of a TCP RST and does not affect the TCP connection") | Unknown             | Passed              |
|[rcv-fin-ack-without-data-syn-sent-ack-outside-right-ipv6](rcv-fin-ack-without-data-syn-sent-ack-outside-right-ipv6.pkt "Ensure that the reception of a TCP FIN-ACK with SEG.ACK=RCV.NXT+1 in the SYN-SENT state triggers the sending of a TCP RST and does not affect the TCP connection") | Unknown             | Passed              |
|[rcv-fin-ack-with-data-syn-sent-ack-outside-left-ipv4](rcv-fin-ack-with-data-syn-sent-ack-outside-left-ipv4.pkt "Ensure that the reception of a TCP FIN-ACK with SEG.ACK=SND.NXT-1 in the SYN-SENT state triggers the sending of a TCP RST and does not affect the TCP connection")         | Unknown             | Passed              |
|[rcv-fin-ack-with-data-syn-sent-ack-outside-left-ipv6](rcv-fin-ack-with-data-syn-sent-ack-outside-left-ipv6.pkt "Ensure that the reception of a TCP FIN-ACK with SEG.ACK=SND.NXT-1 in the SYN-SENT state triggers the sending of a TCP RST and does not affect the TCP connection")         | Unknown             | Passed              |
|[rcv-fin-ack-with-data-syn-sent-ack-left-edge-ipv4](rcv-fin-ack-with-data-syn-sent-ack-left-edge-ipv4.pkt "Ensure that the reception of a TCP FIN-ACK with SEG.ACK=SND.NXT in the SYN-SENT state does not affect the TCP connection")                                                       | Unknown             | Passed              |
|[rcv-fin-ack-with-data-syn-sent-ack-left-edge-ipv6](rcv-fin-ack-with-data-syn-sent-ack-left-edge-ipv6.pkt "Ensure that the reception of a TCP FIN-ACK with SEG.ACK=SND.NXT in the SYN-SENT state does not affect the TCP connection")                                                       | Unknown             | Passed              |
|[rcv-fin-ack-with-data-syn-sent-ack-outside-right-ipv4](rcv-fin-ack-with-data-syn-sent-ack-outside-right-ipv4.pkt "Ensure that the reception of a TCP FIN-ACK with SEG.ACK=SND.NXT+1 in the SYN-SENT state triggers the sending of a TCP RST and does not affect the TCP connection")       | Unknown             | Passed              |
|[rcv-fin-ack-with-data-syn-sent-ack-outside-right-ipv6](rcv-fin-ack-with-data-syn-sent-ack-outside-right-ipv6.pkt "Ensure that the reception of a TCP FIN-ACK with SEG.ACK=RCV.NXT+1 in the SYN-SENT state triggers the sending of a TCP RST and does not affect the TCP connection")       | Unknown             | Passed              |
