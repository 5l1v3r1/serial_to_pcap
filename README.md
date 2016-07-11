# serial_to_pcap
Convert serial communication traffic to pcapng that could be read and analyzed by Wireshark.
Wirtten by AutoHotKey scripts.
Currently supported protocol: 
  1) DNP3.0
  2) IEC 60870-5-101
  3) IEC 60870-5-103
  4) IEC 60870-5-104
  5) Modbus TCP

Note: This tool will call text2pcap that comes with Wireshark installation.
Default execute path is "C:\Program Files\Wireshark\text2pcap.exe".(Maybe consider put path in a text file) 
  
Input format:

[13:53:45.063] Rx <= 
68 12 12 68 08 01 0A 81 02 01 FE F1 00 01 02 
01 01 04 02 01 AA 2A 66 16
[13:53:45.065] Tx <= 
68 12 12 68 08 01 0A 81 02 01 FE F1 00 01 02 
02 01 04 02 01 AA 2A 67 16

Time stampe need start with [, and with Rx or Tx in the line;
Current support 15 data per line, can be configured in the future;

The input file will be formatted to a temperaory file with different name, added '_n' at the input filename.

The output will be pcapng file.