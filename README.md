# Wireshark Packet Analysis Lab







## Project Overview

This project demonstrates network packet analysis using Wireshark.  
The lab focuses on inspecting packet captures (PCAP files), understanding how data moves across the network, and using Wireshark tools to investigate network traffic.

During the analysis, packets were inspected across multiple protocol layers, HTTP traffic was analyzed, and filtering techniques were used to isolate specific communication streams.

This lab was completed as part of a learning exercise from TryHackMe and recreated independently for documentation and portfolio purposes.

---
## Tools & Technologies

- Wireshark  
- Linux Ubuntu Virtual Machine  
- Packet Capture (PCAP) analysis  
- Terminal utilities for hash verification and file inspection  

---

## Learning Objectives

The main goals of this lab were:

- Navigate and understand the Wireshark interface
- Inspect packet structure across protocol layers
- Analyze HTTP traffic inside packet captures
- Use display filters to isolate network activity
- Follow TCP streams to reconstruct communications
- Use terminal commands to verify hashes and inspect files within captures

---

## Wireshark Interface Overview

Wireshark provides several panels that allow analysts to examine network traffic in detail.

The main interface consists of:

- **Packet List Pane** – Displays a summary of captured packets including source, destination, protocol, and packet information.
- **Packet Details Pane** – Shows a detailed breakdown of the selected packet.
- **Packet Bytes Pane** – Displays the raw packet data in hexadecimal and ASCII format.









---

## Packet Dissection

Packet dissection allows analysts to break down packets into their individual protocol layers.  
This helps identify how data is structured and transmitted across the network.

During this lab, packets were analyzed according to the OSI model layers including:

- Frame Layer
- MAC Address (Layer 2 – Data Link)
- IP Address (Layer 3 – Network)
- TCP/UDP Protocol (Layer 4 – Transport)
- Application Protocol (Layer 7 – HTTP)

Each layer provides important information such as source and destination addresses, ports, and application data.








---

## HTTP Traffic Analysis

One of the primary tasks in this lab was analyzing HTTP traffic inside the packet capture.

By selecting HTTP packets and inspecting their details, it was possible to identify:

- Server responses
- HTTP headers
- Packet payload size
- TTL values
- Metadata such as ETag values

This type of analysis helps security analysts understand how web communication occurs across a network.








---

## Packet Navigation and Investigation

Wireshark provides multiple tools that make it easier to navigate large packet captures.

Some of the techniques used in this lab include:

- **Go to Packet** – Navigate directly to a specific packet number.
- **Find Packet** – Search packets using strings, hex values, or expressions.
- **Mark Packet** – Highlight important packets for further investigation.
- **Packet Comments** – Add notes for specific packets.

These features are particularly useful when analyzing captures containing thousands of packets.









---

## Packet Filtering

Wireshark uses a powerful filtering system that allows analysts to isolate specific traffic.

Some basic display filters used during this lab include:

```
http
tcp.port == 80
ip.addr == 192.168.x.x
```

Filtering reduces noise in packet captures and helps analysts focus only on relevant network activity.










---

## Stream Reconstruction

Wireshark can reconstruct communication streams between hosts.

Using the **Follow TCP Stream** feature, the full communication between a client and server can be reconstructed, allowing analysts to view the data exchanged during the session.

This feature is useful for:

- Understanding web requests and responses
- Identifying credentials transmitted in plaintext
- Investigating suspicious communications









---

## Terminal Investigation

Some parts of the investigation required using the Linux terminal.

### Finding File Hash (MD5)

To verify the integrity of a file referenced in the capture, the following command was used:

```
md5sum <filename>
```

This command generates an **MD5 hash**, which can be used to confirm whether a file has been modified or corrupted.









---

### Investigating Files in the Capture

A `.txt` file embedded in the packet capture was discovered during analysis.

After extracting and examining the file, the hidden content revealed the alien name:









This demonstrates how network captures may contain hidden or transferred files that analysts must inspect during investigations.

---

## Key Findings

During the investigation the following observations were made:

- HTTP traffic was successfully identified within the capture.
- Packet metadata such as TTL values and payload sizes were analyzed.
- Stream reconstruction revealed server responses containing artist data.
- Embedded files were located and examined.
- Terminal tools were used to verify file hashes.

---

## Skills Demonstrated

This project demonstrates several fundamental cybersecurity and network analysis skills:

- Network packet analysis
- Protocol inspection
- HTTP traffic investigation
- Packet filtering
- TCP stream reconstruction
- Basic digital forensics techniques

---

## Credits

This lab is based on the **Wireshark Basics** learning room from TryHackMe.

The analysis and documentation in this repository were recreated independently for learning and portfolio purposes.

---
