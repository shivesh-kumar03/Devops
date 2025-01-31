**Networking Fundamentals**

This series of lessons will cover the fundamentals of networking, which are essential for anyone who want to learn or get into Cloud or DevOps domain. Understanding basic networking is foundational, as it represents the starting and ending points for data moving across the internet. Data travels across interconnected networks on the internet. The series will cover how data is prepared for transit, network ports, and sessions to ensure reliable data transfer for applications.

**OSI 7-Layer Model**

The best way to understand networking is through the OSI 7-Layer model. This model divides networking into seven distinct components, starting from the physical layer at the bottom and progressing to the application layer at the top. The OSI model is a conceptual framework and not necessarily how networking software is implemented. It provides a strong base for understanding how each component works and interacts with others. The seven layers, from bottom to top, are: Physical, Data Link, Network, Transport, Session, Presentation, and Application.

![Image](https://github.com/user-attachments/assets/77bb7598-829f-47bd-96db-382c38a54939)
     **OSI-Layers with different processes in each layer**

The software performing the functions of these layers is known as the networking stack. Devices like laptops, phones, Wi-Fi routers, and servers all have a networking stack.

The layers are divided into two groupings:

- **Media Layers:** These include the Physical, Data Link, and Network layers. They deal with how data is moved between points, whether on a local network or across the globe.
- **Host Layers:** These include the Transport, Session, Presentation, and Application layers. They handle how data is divided, reassembled, and formatted for network communication.

**Data Flow**

At the top of the stack (Layer 7), you might have a web browser like Firefox, and a web server at the other end. At the bottom (Layer 1), there are physical network cards or interfaces. Data from the browser flows down through the layers on one side, then goes to the other side, and then flows up to the web server software. This flow is conceptual. Understanding these layers and their functions will provide a real foundational understanding of how networking works.
