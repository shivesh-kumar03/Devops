**IP Addressing and Structure**

- IP addressing identifies devices using Layer 3 IP networking. An IP address allows packets to start their journey to a destination, though firewalls, security restrictions.
    
- The format of an IPv4 address is known as dotted decimal notation, with four decimal numbers from 0 to 255 separated by dots. For example: 133.33.3.7.
    
- An IP address has two parts: the **network part**, which indicates which IP network the address belongs to, and the **host part**, which identifies a host on that network.
    
- The network part of an IP address determines if two devices are on the same network. If the network parts of two IP addresses match, the devices are on the same network.
    
- IP addresses are actually binary numbers, not dotted decimal. Each decimal part is an 8-bit binary number, called an octet. An entire IPv4 address is 32 bits (4 octets) in size. For example, the first octet of 133.33.3.7 is 133, which is 10000101 in binary.
    
- A slash prefix (e.g., /16) indicates how many of the first bits of the IP address represent the network. For example, a /16 prefix means the first 16 bits are the network, and the rest are for hosts.
    

**Subnet Masks**

- Subnet masks help determine if IP addresses are local or remote. They are configured on Layer 3 interfaces along with IP addresses.
    
- A subnet mask identifies which part of the IP address is the network and which is the host.
    
- Subnet masks are also binary numbers, converted from dotted decimal. For example, 255.255.0.0 in binary is 11[111111.1111](tel:1111111111)1111.00[000000.0000](tel:0000000000)0000.
    
- The prefix notation (/16) is shorthand for the number of ones in the binary form of the subnet mask.
    
- When a subnet mask and IP address are overlaid, with both in binary, the 1s in the subnet mask represent the network part, and the 0s represent the host part.
    

**Calculating Network Start and End IPs**

- To find the start of a network, take the network part of the IP address (as indicated by the 1s in the subnet mask) and set all the host bits (where the subnet mask has 0s) to zeros.
    
    - For the IP address 133.33.3.7 with a subnet mask of 255.255.0.0, the network starts at 133.33.0.0.
- To find the end of a network, take the network part of the IP address and set all host bits to ones.
    
    - For the IP address 133.33.3.7 with a subnet mask of 255.255.0.0, the network ends at 133.33.255.255.

**Default Gateways**

- A default gateway is an IP address on the local network that packets are sent to if the destination IP address is not local.
    
- On a home network, the internet router is usually the default gateway.
    

**IP Routing**

- Routers use **route tables** to determine where to forward packets.
    
- Route tables contain routes, each with a destination and a next hop (or target).
    
- When a packet arrives at a router, the router checks the packet's destination IP address and looks for matching routes in the route table.
    
- If multiple routes match, the router will prefer the more specific route (larger prefix).
    
    - A /32 is the most specific, representing a single IP address, while a /0 is the least specific, representing all IP addresses.
- A default route (0.0.0.0/0) matches all IP addresses and is used if no other route matches.
    
- Routers forward packets hop-by-hop from source to destination, using route tables to find the next hop.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738417117277/b721688c-4aaa-4d54-a759-66270e40a0cd.png?auto=compress,format&format=webp)

**Address Resolution Protocol (ARP)**

- ARP finds the MAC address for a given IP address. This is used when a device needs to send a frame to another device.
    
- When a device needs to send data to another on the same local network, it uses ARP to find the destination MAC address.
    
- ARP broadcasts an ARP frame asking for the MAC address associated with an IP address. The device with that IP address responds with its MAC address.
    
- If two devices are on the same local network, they will use one Layer 2 frame per packet.
    

**Routing Example**

- Packets may be re-encapsulated in different Layer 2 frames along the way from source to destination.
    
- When a device on one network needs to send data to a device on a different network, it sends the packet to its default gateway, the router.
    
- The router uses the route table to find the next hop router.
    
- The packet will travel through multiple Layer 2 networks, each time being encapsulated in a new Layer 2 frame and decapsulated.
    
- Routers understand physical networking, data link networking, and IP networking.
    

**Layer 3 (Network Layer)**

- Layer 3 gets data from one location to another. It allows you to connect to remote networks across intermediate networks.
    
- Layer 3 uses IP addresses for cross-network addressing.
    
- Layer 3 is a common protocol that spans multiple different Layer 2 networks.
    
- IP packets have source and destination IP addresses.
    
- The protocol field in a packet indicates which Layer 4 protocol is being used (e.g., TCP, UDP).
    
- The Time to Live (TTL) field limits how many hops a packet can go through before being discarded.
    
- Packets are encapsulated in Layer 2 frames as they move through Layer 2 networks.
    

![TCP Header](https://cdn.hashnode.com/res/hashnode/image/upload/v1738417150679/51502f1b-c1d2-4639-a4b4-6904968daed1.png?auto=compress,format&format=webp)

**TCP Header**

![UDP Header](https://cdn.hashnode.com/res/hashnode/image/upload/v1738417188967/07c535c4-030d-43d0-87fd-bd3623623d7b.jpeg?auto=compress,format&format=webp)

**UDP Header**

**Summary** IP addressing and subnet masks are fundamental to Layer 3 networking. IP addresses uniquely identify devices, while subnet masks define the network and host portions of those addresses. Routers use route tables and the Address Resolution Protocol (ARP) to forward packets across networks, encapsulating them within different Layer 2 frames at each hop. Layer 3 enables communication between devices on different networks and provides a common protocol that can span different Layer 2 networks. Packets, containing data from Layer 4 protocols, have source and destination IP addresses and move from source to destination through various intermediate networks, and the Time To Live field ensures they are discarded if they cannot reach the destination in a limited number of hops.