# Display filters
By default Wireshark will display all packets. If you want to show only specific protocol packets type the 
name of the protocol at the filter input at the top. For example, `tcp` then enter, will only display tcp 
packets. Other filters can be `udp, icmp, http, dns`

You can be more specific and filter based on some flags in the packet. For example
 `dns.flags.response == 0` will display the dns queries that don't have mached responses. 

You can build the filter by right clicking on the flag you want in the bottom pane, then select `Apply filter`  
then `Select`. 

# Command line.
Tshark doesn't support filtering while reading file, one way around this is. However, it does support filtering 
while writing. 
```
tshark -nr smallFlows.pcap -w - "dns"| tshark -r -
tshark -nr smallFlows.pcap -w - "dns.flags.response == 0"| tshark -r -
```
