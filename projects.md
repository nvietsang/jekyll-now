---
layout: page
title: Projects
permalink: /projects/
---
## Personal

## Internship
[Research Institute XLIM](https://www.xlim.fr) - Researcher Intern
+ **Pre-filtering in Pub/Sub systems:** Implemented an encrypted matching scheme. Embedded Bloom Filter and Cuckoo Filter into broker in order to pre-discard costly matching operation in case of being known definitely not to match. Compared the two filters’ performances. [Report](https://nvietsang.github.io/pdfs/Report_Intern_Prefiltering.pdf)

[Knorex](https://www.knorex.com) - Researcher Intern
+ **Language Detection:** Fixed bugs. Evaluated and improved 60% in accuracy when detecting Malaysian and Indonesian.  Added the ability to detect 5 new languages.

+ **Key Mining:** Evaluated and improved 10-20% in accuracy to extract keywords related to a certain topic in passages. Added the ability to extract keywords for 5 new languages.

+ **Document Filtering:** Prepared data to feed [DAZER model](http://aclweb.org/anthology/P18-1214).

## Ho Chi Minh University of Technology (HCMUT)
These are educational projects which I did in different courses at HCMUT.
+ **Question-Answering (thesis):** Re-implemented the Deep Learning model [QANet](https://research.google/pubs/pub46691/) to predict an answer for a question with a English passage based on the dataset [SQuAD](https://rajpurkar.github.io/SQuAD-explorer/); Built a dataset for Vietnamese (about 10K samples). Built a model based on QANet working on Vietnamese (Exact Match 61.0%, F1-score 76.6%). [Demo](http://qa-vi.herokuapp.com) [Report](https://nvietsang.github.io/pdfs/ViQA_Paper.pdf)

+ **Smart Light (Global Project Based Learning):** Led a team of 6 members, including Vietnamese and Japanese students.  Designed a system with automatic light control and alarm for theft warning.  Built an Arduino circuit and wrote C program. [GitHub](https://github.com/nvietsang/smart-light-project) [Demo](https://www.youtube.com/watch?v=gqi_0X2tpN4)

+ **Mini C (Principles of Programming Languages course):** Used Scalar to implement the interpreter/compiler of a new language called **Mini C** which consists of a subset of C plus some Java language features. Implemented and wrote test cases for lexical analyzer by using [ANTLR](https://www.antlr.org), syntax analyzer by generating abstract syntax tree (AST), semantic analyzer (e.g. type compatibility, scope constraints), code generator (for a stack-based machine like JVM).

+ **Bus Ticket Booking Application (Software Engineering course):** Worked with a team of 5 members. Designed ERD/EERD and implemented database with SQL. Used Servlet to implement server features with Java.

+ **LineXO (Mobile Application Development course):** Worked with a team of 4 members to build an Android application of game. Designed database and implemented with Firebase. [GitHub](https://github.com/nvietsang/linexo) [Slide](https://github.com/nvietsang/linexo/blob/master/Presentation/LineXO/LineXO.pdf)

## University of Limoges (UNILIM)
These are educational projects which I did in different courses in UNILIM. Personally, I think most of them are really interesting. I feel like I learned a ton of things when finishing them. 

+ **NIDS based on Deep Learning:** Built a real-time Network Intrusion Detection System (NIDS). Combined AI and Big Data technologies. Implemented with [Snort](https://www.snort.org) (to detect suspect traffic), Kafka (to coordinate data thanks to consumer and producer), Deep Learning (to build model based on dataset [KDDCup99](http://kdd.ics.uci.edu/databases/kddcup99/kddcup99.html) and predict type of attacks), Zeek (to transform pcap to readable data), Spark (to convert data to KDD99Cup's format). [Demo](https://www.youtube.com/watch?v=5G5mZ2JT_jo) [Report](https://nvietsang.github.io/pdfs/Report_ADL.pdf)

+ **ISD & MDPC (Advanced Cryptology course, 19/20):** Implemented the attack Information Set Decoding (ISD) based on inverse of matrix and weight of error; Implemented the protocol of key exchange [BIKE-2](https://bikesuite.org) (a variant of Moderate Density Parity-Check - MDPC). Studied and did experiments on the core of the Bit Flipping Algorithm (threshold *T* and parameter *w*). <!-- [Report](https://nvietsang.github.io/pdfs/Report_CryptoAv.pdf) -->

+ **Image Filtering (GPGPU course, 20/20):** Utilised parallel computing to apply filters (e.g soften, sharpen, Sobel) on images with CUDA. Improved speed of computation through different versions (CPU, OpenMP, Naive CUDA, Shared memory on CUDA). Did experiments and comparisons. <!-- [Report](https://nvietsang.github.io/pdfs/Report_GPGPU.pdf) -->

+ **Tunnel L2TPv3 secured by IPsec (Network Infrastructure course, 17.5/20):** Built a network with VLANs by *netnamespaces* and *open vswitch* in Linux. Built a L2TPv3 tunnel for Vitual Private Networks (VPNs). Implemented IPsec to secure traffic of the tunnel. Configured DHCP servers for different VLANs. Implemented different encapsulation modes of L2TPv3 (IP and UDP) and GRETAP, explored packets with *tcpdump* and *Wireshark* and did comparisons. Studied transfering speed of encrypted packets by command *iperf*. Configured the address translation in NetFilter by *iptables* in order to access the Internet. Optimized the routs of accessing Internet by *dnsmasq*. Prevented traffic between different VLANs by rules of firewall and *Policy Routing*. <!-- [Report](https://nvietsang.github.io/pdfs/Report_Infra.pdf) -->

+ **Transparent Proxy (Avanced Network 1 course):** Built a private network by *netnamespaces* and *open vswitch* in Linux. Configured a DHCP server with *dnsmasq*. Configured the firewall and address translation in NetFilter by *iptables* in order to access the Internet and redirect traffic. Implemented a server as a Proxy to require authentification before accessing the Internet. <!-- [Report](https://nvietsang.github.io/pdfs/Report_ResAvI.pdf) -->

+ **Brute-force attack to WiFi password (Avanced Network 2 course):** Given captured traffic (pcap) of WiFi connection. Studied the protocol of exchange *WPA-PSK*. Used Scapy to analyze packets and brute-force. <!-- [Report](https://nvietsang.github.io/pdfs/Report_ResAvII.pdf) -->

+ **CertifPlus (Security of using ICT course, 17/20):** Built a back-end server to securely distribute and verify electronic attestations using signatures and timestamps. Generated keys and certificates for Certificate Authentity (CA) and server by [openssl](https://www.openssl.org). Applied steganograhpy to hide signatures and QRcode to hide timestamp. Requested and verify timestamp by [https://www.freetsa.org](https://www.freetsa.org). Built a frontal server to avoid direct interactions between clients and back-end server. [Demo](https://youtu.be/_Zw2cijWcmE) <!-- [Report](https://nvietsang.github.io/pdfs/Report_TIC.pdf) -->

+ **Image Texture Synthesis (Avanced Algorithm and Programmation course):** Designed and implemented a dynamic programming algorithm for image texture synthesis based on the paper [Image Quilting for Texture Synthesis and Transfer](https://people.eecs.berkeley.edu/~efros/research/quilting.html). Implemented different algorithms (recursion, recursion with redundant calculation, iteration), did experiments and comparisons.

+ **TriviaLim (Advanced Java course, 17/20):** Built an Android gaming application of answering multiple-choice questions. Designed the architecture of database and the script. Applied fragments to control activities. Used Firebase as database. [apk](https://nvietsang.github.io/pdfs/TriviaLim.apk) <!-- [Report](https://nvietsang.github.io/pdfs/Report_JavaAv.pdf) -->

+ **Game of Labyrinth (Artificial Intelligence 1 course):**
Implemented different searching algorithms (Best-First Search, A\*, Breath-First Search, Depth-First Search). <!-- [Report](https://nvietsang.github.io/pdfs/Report_AI1.pdf) -->

+ **Learning Algorithms (Artificial Intelligence 2 course):** Implement unsupervised algorithm (K-means) and supervised algorithms (Perceptron, Neuron Network) to classify. Did experiments and comparisons. <!-- [Demo](https://youtu.be/GNThQGsgZD4)  -->

+ **NashE and Dom (Game Theory course, 17/20):** Computed pure Nash equilibrium, mixed Nash equilibrium, dominated strategies and check if a game is zero-sum. Applied to different types of games (2 players - 2 actions, 2 players - many actions, many players - many actions).[Demo](https://youtu.be/blwCa2zhBn8) <!-- [Report](https://nvietsang.github.io/pdfs/Report_GameTheory.pdf) -->

