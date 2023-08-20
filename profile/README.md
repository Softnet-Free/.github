# Softnet Free
Softnet Free is an IoT communication platform for devices with embedded TCP/IP stack. It implements a software-defined networking environment that enables direct communication between devices. Softnet makes the TCP and UDP protocols available for use in dynamic IP environments. The platform offers Remote Procedure Calls and Application Events as additional IPC mechanisms. The latter is used in event-driven interaction scenarios. The Softnet mechanism of Access Control can be used to implement different levels of access to devices, and a mechanism called Service Status Detection provides clients with information about the connectivity status of remote devices. Softnet also provides a convenient solution for managing devices, clients, user permissions, and shared access to devices with other individuals/organizations. The latter allows owners to establish user-to-user or business-to-customer relationships. Using Softnet, developers can focus on IoT application logic without concerning about networking issues.  

Softnet Free is licensed under Apache License, Version 2.0. You can use, modify and distribute the server software and the endpoint libraries without any restrictions. We’ll be glad if you participate in the further development and improvement of the project.

As of June 2023, the [Softnet endpoint library](https://github.com/Softnet-Free/softnet-java/) is available in Java SE 1.7. It works on Linux platforms, Raspbian, Android 5.0 and later versions. The endpoint libraries for other platforms are under development. First of all, we focus on FreeRTOS, ChibiOS/RT and other RTOS platforms widely used in industrial microcontrollers such as STM32, PIC32, EFR32, Infineon XMC, TI SimpleLink, ESP32, etc.

## Resources for developers

If you want to know more about the Softnet platform, the following sources will be helpful:
* [Softnet Programming Model (Java)](https://softnet-free.github.io/softnet-java/) / This guide describes the process of developing IoT applications using Softnet Java Library;
* [The Developer Guide to Softnet ASN.1 Codec (Java)](https://softnet-free.github.io/asn1codec-java/) / This guide provides the specification for the API of Softnet ASN.1 Codec (Java). As an option, Softnet allows you to use the ASN.1 DER format to transfer data over a network, although you can use any other format, such as JSON;

## A brief description of the platform

In recent years, TCP/IP-enabled embedded systems have been increasingly used in industrial automation as well as consumer electronics. Modern embedded systems, built even on low-cost microcontrollers, can be powerful enough to implement on-device business logic for autonomous operation, interact with the physical environment, and communicate with clients over IP networks. However, the communication model used for interacting with such devices over the Internet is entirely different from that used to communicate with stationary Internet services. At first glance, establishing connectivity in a dynamic IP environment is a major challenge that developers face when designing networking capabilities for embedded systems. In fact, along with connectivity, there are a number of other challenges that we’ll consider a little later. IoT developers are good at GPIO programming, but don't really like to go deep into solving complex TCP/IP networking tasks.  

Typically, device manufacturers use cloud platforms to ensure the networking capabilities for their products. In addition, a cloud platform can store application data, apply analytics to the data, and use artificial intelligence to take decisions. While suitable platforms may already exist for some popular IoT applications, such as platforms for controlling drones over 4G networks, new ideas in IoT are being born all the time. The development of a communication platform is a complex and expensive task even when the devices to be networked are relatively simple. This can be a major barrier for start-ups, small-scale manufacturers and Do-It-Yourself developers.  

The good news is that the communication tasks we are talking about can be organized, structured, and implemented within a single, unified platform. This platform could be used on its own, as well as integrated into application-specific cloud platforms or run as a service with a unified API to serve other platforms that require networking capabilities for embedded systems. These considerations form the basis of the Softnet Free concept.  

Let’s see what Softnet Free offers to developers and users.  

**Software-defined network**. Unlike a typical database-driven Internet service, an embedded system connected to the Internet provides access to the resources of an electromechanical device. Usually these resources are quite limited, hence the networked device has a rather limited set of clients. Each client is supposed be approved by the device owner and assigned certain access rights. Softnet implement this idea within the concept of Site, which serves as a framework that establishes a software-defined network with an enclosed address space. An IoT project can contain multiple sites. The device owner creates a site to set up one device or multiple identical devices. The devices are represented on the site as services. The device consumers, in turn, set up clients on sites that host the services they want to consume according to their permissions. All services on a site must support the same interface. All clients on the site, in turn, must be designed to consume the given interface.  

**TCP and UDP in dynamic IP environments**. Almost any application-level protocol uses TCP or UDP as a transport protocol. However, if a remote device is situated behind firewalls and/or NATs, it may become unreachable for clients to establish transport-level connections. There is also an IPv4/IPv6 inter-stack communication issue. Softnet solves these issues behind the scene. A client simply requests the platform to establish a connection. If the remote device authorizes the request, Softnet establishes the connection in P2P mode, and if this is not possible, then in proxy mode and returns the connected sockets to the client and the remote device. Devices listen for TCP/UDP connection requests on virtual ports. Bindings to fixed physical ports aren't used. This approach ensures reliable protection against Brute-Force and DDoS attacks on the devices. Softnet also supports IPv4/IPv6 inter-stack connections for both TCP and UDP protocols without the need for special IPv4/IPv6 transition equipment.  

**Remote Procedure Calls**. Due to limited resources, some industrial microcontrollers may not be able to communicate using standard application layer protocols. In such a case, Softnet offers to use a built-in RPC mechanism. The procedure parameters and return value are in ASN.1 format, which allows for compact representation of complex hierarchical data. Softnet provides developers with a convenient tool called Softnet ASN.1 Codec to work with ASN.1 format.  



<!--

**Here are some ideas to get you started:**

🙋‍♀️ A short introduction - what is your organization all about?
🌈 Contribution guidelines - how can the community get involved?
👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
🍿 Fun facts - what does your team eat for breakfast?
🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
-->
