# 1- Caputer file properties:
First thing you may want to do after opening the pcap file is to go to `Statistics -> Caputre File Properties` 
to see a summary of the pcap file. For example, size, hash, time of first and last packet, number of packets
average size etc. 

## Command line
Use the following command to get capture file properties from the shell.
```
capinfo smallFlows.pcap 
```
To read the pcap file use.
```
tshark -nr smallFlows.pcap 
# -n to disable name resolution.
```
Note that `tshark`, `capinfos`, `editcap`, and `mergecap` all tools installed with wireshark to be used from 
command line. 

# 2- Protocol Hierarchy Statistics
To view what type of protocols exist in the pcap file along with the number of packets and the percentage of
 each protocol contripution to the total number of packet go to `Statistics -> Protocol Hierarchy`

## Command line 
 ```
tshark -z io,phs -rn smallFlows.pcap
 ```
