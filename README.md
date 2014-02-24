bitcoin-wireshark-dissector
===========================

Bitcoin wireshark 1.10.5 dissector with better support for the bitcoin protocol.  Also DogeCoin/Litecoin support.


I was looking around for something to monitor my bitcoin traffic and figured there would be something out there
for Wireshark.  Unfortunately like much of the bitcoin source everything I could find was a couple years old and out 
of date.  

The current dissector in 1.10.5 is really wrong and can't even decode some of the basic messages correctly.  The dissector
in the development tree has fixes for the basic messages but doesn't do much more than that.

So I spent a couple days poking at the source of the 1.10.5 dissector and came up with this.  It's not perfect, in fact
it's not even good but it's better than what I could find. I started it as a plug-in but then just switched to replacing the built-in dissector.


Additions over the existing dissector in 1.10.5:

Added Litecoin/Dogecoin magics 
Fixed correct parsing of version/verack messages
Added parsing for commands:
  notfound,ping,pong,reject,alert
  
  
Installing ==

Download the 1.10.5 source...

replace the file  epan/dissectors/packet-bitcoin.c found in the wireshark source directory with this one

make and sudo make install

you should be good to go...


If anyone wants to drag this over to the wireshark source tree feel free.

Monty

1AdWh9zAPCGKwHLagugoDNzpeyokwhbwNP

D6kTfuNz3dhvoqvjpY5kWRp68KhsDHFEty



