Softnet Free is an IoT communication platform for devices with embedded TCP/IP stack. It implements a software-defined networking environment for direct communication between devices. Softnet makes the TCP and UDP protocols available for use in dynamic IP environments. The platform offers built-in Remote Procedure Calls as an additional IPC mechanism, as well as Pub/Sub Events used to implement event-driven interaction scenarios. The platform also supports notifications used in asynchronous communication. The Softnet mechanism of Access Control can be used to implement different levels of access to device resources, and a mechanism called Service Status Detection provides clients with information about the status of remote devices. Softnet also provides a convenient solution for managing devices, clients, user permissions, and shared access to devices with other individuals/organizations. The latter allows owners to establish user-to-user or business-to-customer relationships. Using Softnet, developers can focus on IoT application logic without concerning about networking issues.  

The following features of the platform can be considered as innovative:

- Centralized management of user permissions leveraging the inherent user roles embedded in the devices;
- A packet switching technique for relaying TCP connections. This technique is much more resource-efficient compared to the connection-switching method employed by a TURN relay for TCP connections;
- Framework for seamless integration of widely used protocols like HTTP, WebSocket, SSH, RTSP, etc., within the IoT/IIoT domain, along with the corresponding software and utilization techniques. The integration of the protocols themselves is currently under development.   

Softnet Free is licensed under Apache License, Version 2.0. You can use, modify and distribute both the server software and the endpoint libraries without any restrictions.

As of October 2023, the Softnet endpoint library built in Java SE 1.7 is available. It works on Linux platforms, embedded Linux, Armbian, Raspbian, Android 5.0 and later versions. The endpoint libraries for other platforms are under development. First of all, we focus on FreeRTOS, ChibiOS/RT, Contiki and other platforms widely used in industrial microcontrollers such as STM32, TI SimpleLink, Infineon XMC, ESP32, PIC32, EFR32, etc.

## Resources for developers and users

1. [Softnet Free Demo Server](http://ts.softnet-iot.org) / This is a demo server with free registration where you can try out Softnet applications and see if the platform's functionality meets your requirements;
2. [The User Guide to Softnet Management System](https://softnet-free.github.io/softnet-ms/) / This guide explains how to use **Softnet MS** for managing devices and clients utilizing the Softnet platform. It is designed for both developers and users;
3. [Discussions](https://github.com/orgs/softnet-free/discussions) / Here, you can ask [questions](https://github.com/orgs/softnet-free/discussions/categories/q-a), view [demo examples](https://github.com/orgs/Softnet-Free/discussions/categories/basic-examples), participate in discussions, etc.;
4. Resources for embedded Java application development:
    * [Softnet Endpoint Library (Java)](https://github.com/Softnet-Free/softnet-java/) / The Softnet endpoint library built on Java SE 1.7. It works on Linux platforms, Raspbian, Android 5.0 and later versions;
    * [Softnet Programming Model in Java](https://softnet-free.github.io/softnet-java/) / This guide explains the process of developing applications using **Softnet Endpoint Library (Java)**;
    * [Softnet ASN.1 Codec (Java)](https://github.com/softnet-free/asn1codec-java) / The ASN.1 codec written in Java. Softnet uses it to encode/decode messages in the ASN.1 DER format for transmission over a network. This tool can also be used to encode/decode application data for transmission over a network, although you can use any other format, such as JSON;
    * [The Developer Guide to Softnet ASN.1 Codec (Java)](https://softnet-free.github.io/asn1codec-java/) / This guide explains how to use **Softnet ASN.1 Codec (Java)** in the application development;
    * A brief developer guide is also published on [hackster.io](https://www.hackster.io/robert-koifman/softnet-free-empowering-iot-with-tcp-ip-connectivity-46a62c).
5. Resources for deploying Softnet servers on the Microsoft Windows platform:
    * The administrator guide for deploying and managing Softnet servers is **coming soon**;
    * [Softnet Tracker](https://github.com/Softnet-Free/softnet-tracker-c-sharp) / This server implements the core business logic of Softnet Free;
    * [Softnet Proxy](https://github.com/Softnet-Free/softnet-proxy-c-sharp) / This server implements mechanisms for establishing TCP and UDP connections in peer-to-peer and proxy mode;
    * [Softnet Management System](https://github.com/Softnet-Free/softnet-ms-aspnet) / Softnet MS provides users with tools for managing devices and clients utilizing the Softnet platform;
    * [Softnet ServerKit](https://github.com/Softnet-Free/serverkit-c-sharp) / This library contains classes and algorithmes used by the Softnet servers;
    * [Softnet ASN.1 Codec (C#)](https://github.com/Softnet-Free/asn1codec-c-sharp) / This codec is used by the Softnet servers to encode/decode messages in the ASN.1 DER format for transmission over a network;
    * [Administration Tool](https://github.com/Softnet-Free/admin-tool-c-sharp) / This tool is used to initially set up the platform database and assign/revoke the "Administrator" role to users;
    * [Database Generation Script](https://github.com/Softnet-Free/database-script-mssql) / This is an SQL script for creating a Softnet database in MS SQL Server.

## A brief review of the platform

The Internet of Things is essentially a concept that describes a system of interconnected devices that use the Internet for communication. But, oddly enough, one of the primary challenges of IoT is precisely ensuring this Internet-based communication between devices.
In this review, I’d like to present you Softnet Free, a communication platform designed for devices with an embedded TCP/IP stack. Typically, an IoT platform is developed to solve some real IoT problem. Although there are many IoT platforms in the market, the problem discussed in this review is relatively new and has emerged recently due to the proliferation of TCP/IP-enabled smart devices. Nowadays, nearly every MCU manufacturer offers a range of MCUs equipped with TCP/IP interfaces. Embedded systems built on them typically have enough capacity to implement on-device business logic, interact with the physical environment, and communicate with clients over IP networks. These MCUs are increasingly used in industrial automation as well as in the production of consumer devices.
The platform’s functionality divided into two logical parts: Core Functionality and Protocol Extensions. The first part is now implemented and available for use in Java applications while the second part is under development.

### Core Functionality

In most cases, an IoT device equipped with TCP/IP support and on-device business logic is also equipped with an API through which clients can interact with the device over IP networks. However, the communication model used to interact with traditional Internet services cannot be simply transferred to the IoT domain, as this comes with significant connectivity, security, and device management challenges. Softnet Free has been designed to address these challenges. The platform implements a software-defined networking environment for direct communication between devices and provides a range of communication patterns. It makes the TCP and UDP protocols available for use in dynamic IP environments. The platform offers built-in RPC as an additional IPC mechanism, as well as Pub/Sub Events, which is typically used to implement event-driven M2M communication scenarios. The platform also supports notifications used in asynchronous communication. And a mechanism called Service Status Detection provides clients with information about the status of remote devices, allowing clients to attempt real-time communication only when the remote device is online. Devices on the Softnet network are not exposed to the Internet directly, and only clients authorized on the platform can interact with them.
In terms of the functionality described above, Softnet Free might be similar to some of the other platforms on the market. However, Softnet Free stands out due to its centralized management system, which can support the device's built-in mechanism of access control. The platform employs the concept of a domain to organize all devices and their clients related to a specific IoT project. The domain contains a list of users where each user can have access to different devices in the project with different permissions. Users can also be associated with other individuals and organizations, thereby allowing for shared access to devices. The platform allows device owners to assign the device's native roles to domain users, so that clients then connect to devices with those permissions inherited from users. To better understand how this works, let’s look at the following diagram:

![Diagram_1](https://github.com/Softnet-Free/.github/assets/36432155/67331636-ff56-4d27-883e-a371aa1f3275)


<!--

**Here are some ideas to get you started:**

🙋‍♀️ A short introduction - what is your organization all about?
🌈 Contribution guidelines - how can the community get involved?
👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
🍿 Fun facts - what does your team eat for breakfast?
🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
-->
