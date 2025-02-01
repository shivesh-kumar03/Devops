- The transport layer (Layer 4) and session layer (Layer 5) of the OSI model are closely related and often discussed together because of overlapping functionalities. The transport layer runs on top of the network layer (Layer 3) and provides essential support for everyday internet networking. The session layer runs on top of the transport layer and many features are shared between these two layers.
    
- **Limitations of Layer 3 (Network Layer):**
    
    - **Independent Packets:** Layer 3 treats each packet as a separate and isolated unit of data routed independently.
        
    - **No Guaranteed Order:** IP (Internet Protocol) does not guarantee that packets arrive in the same order they were sent.
        
    - **Packet Loss:** Packets can be lost due to network issues, including exceeding the TTL (Time to Live) field.
        
    - **Variable Delivery:** Network conditions may cause delays in delivery, and packets can take different routes.
        
    - **No Application Distinction:** IP packets lack the ability to differentiate between applications running on the same device. All packets from a source IP to a destination IP look the same.
        
    - **No Flow Control:** IP doesn't have flow control, which can lead to data loss if the source sends packets faster than the destination can receive them.
        
- **Layer 4 (Transport Layer) Functionality:** Layer 4 builds upon Layer 3 and introduces two key protocols: **TCP** (Transmission Control Protocol) and **UDP** (User Datagram Protocol). Both use IP as transit.
    
    - **TCP (Transmission Control Protocol):**
        
        - **Reliability:** TCP provides reliability, error correction, and ordered data delivery.
            
        - **Connection-Oriented:** TCP is connection-oriented, requiring a connection to be established before data exchange. This creates a bidirectional channel.
            
        - **Common Use:** It is used for important application protocols such as HTTP, HTTPS, and SSH.
            
- **A port is a designated communication channel that pinpoints particular programs and network services operating on a device, enabling them to interact using standardized network protocols.**
    
    - `The numbering of ports ranges from 0 to 65535. There is a division of ports into three ranges:`
        
        `Well-known ports (0-1023) Registered ports (1024-49151) Dynamic or private ports (49152-65535) Well-known ports are typically associated with services or applications, while, for temporary purposes, we use dynamic or private ports.`
        
        **DevOps involves various tools and technologies that communicate over a network. Some of the common ports used in DevOps operations:**
        
- **Databases:**
    
    - **MySQL:** 3306
        
    - **PostgreSQL:** 5432
        
    - **Microsoft SQL Server:** 1433
        
    - **Oracle:** 1521
        
    - **MongoDB:** 27017
        

**Servers:**

- **SSH (Secure Shell):** 22 (for secure remote access and command execution)
    
- **HTTP (Hypertext Transfer Protocol):** 80 (for unencrypted web traffic)
    
- **HTTPS (HTTP Secure):** 443 (for encrypted web traffic)
    
- **RDP (Remote Desktop Protocol):** 3389 (for remote desktop access)
    

**Monitoring Tools:**

- **Prometheus:** 9090 (for metrics collection and querying)
    
- **Grafana:** 3000 (for visualizing metrics and dashboards)
    
- **Elasticsearch:** 9200 (for search and analytics)
    
- **Kibana:** 5601 (for visualizing Elasticsearch data)
    

**CI/CD Tools:**

- **Jenkins:** 8080 (for the web interface)
    
- **GitLab:** 80 (HTTP), 443 (HTTPS), 22 (SSH)
    
- **GitHub:** 80 (HTTP), 443 (HTTPS), 22 (SSH)
    
- **Travis CI:** Uses various ports, often dynamically assigned
    
- **CircleCI:** Uses various ports, often dynamically assigned
    

**Other Tools:**

- **Docker:** 2375 (unencrypted), 2376 (encrypted) (for communication between Docker client and daemon)
    
- **Kubernetes API Server:** 6443 (for Kubernetes API access)
    
- **Ansible:** 22 (SSH) (for configuration management and automation)
    
- **Chef:** 443 (HTTPS) (for configuration management)
    
- **Puppet:** 8140 (for Puppet agent communication)
    

---

- **UDP (User Datagram Protocol):**
    
    - **Speed:** UDP is faster because it doesn't have the overhead of TCP for reliable delivery.
        
    - **Less Reliability:** UDP is less reliable than TCP.
        

- **TCP Segments:** TCP uses segments to transmit data. These segments are encapsulated within IP packets.
    
    - **Source and Destination Ports:** TCP segments include source and destination port numbers, allowing multiple communication streams between devices. The combination of source and destination IP, along with source and destination ports, defines a unique communication channel.
        
    - **Sequence Numbers:** Each segment has a unique sequence number for error correction, ordering, and identifying a particular segment in the connection.
        
    - **Acknowledgments:** The acknowledgment field indicates that a device has received segments up to a certain sequence number.
        
    - **Flags:** TCP flags control the connection and are used to synchronize sequence numbers.
        
    - **TCP Window:** The TCP window defines the number of bytes a receiver is willing to receive before pausing, implementing flow control.
        
    - **Checksum:** Used for error detection and retransmission.
        
    - **Urgent Pointer:** Allows priority for control traffic within a data transfer.
        
    - **TCP Header:** All of the above fields together comprise the TCP header. The remaining capacity of the segment is used for data.
        
- **TCP Connection Establishment:**
    
    - **Three-Way Handshake:** TCP establishes a connection using a three-way handshake.
        
        1. The client sends a **SYN (synchronize)** segment with a random initial sequence number (ISN).
            
        2. The server responds with a **SYN-ACK** segment, including its own random sequence number, and acknowledges the client's sequence number.
            
        3. The client sends an **ACK** segment to acknowledge the server's sequence number.
            
    - **Data Transfer:** Once the connection is established, data can flow, incrementing sequence numbers and acknowledging with sequence value plus one to allow retransmission if needed.
        
- **Sessions:** TCP connections create the concept of a channel or stream between two devices for data exchange, but they are really built upon a collection of segments.
    
    - **Ephemeral Ports:** When a client initiates a connection, it uses a temporary port (ephemeral port) for communication, while the server uses a well-known port.
        
    - **Bidirectional Communication:** TCP connections are bidirectional, with ports being flipped in use so that responses can be sent back from the server to the client.
        

**Summary:** The transport layer (Layer 4) introduces TCP and UDP protocols to overcome the limitations of Layer 3, mainly by providing reliable, ordered, and connection-oriented data transfer with TCP. TCP utilizes segments with ports, sequence numbers, acknowledgments, and flags, along with a three-way handshake to establish reliable connections. These connections allow the concept of a session between two devices. There is some debate about whether stateful firewalls belong to layer 4 or 5, these two layers are often combined to better understand networking and security.