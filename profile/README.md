# Softnet Free
Softnet Free is an IoT communication platform for devices with embedded TCP/IP stack. It implements a software-defined networking environment that enables direct communication between devices. Softnet makes the TCP and UDP protocols available for use in dynamic IP environments. The platform offers Remote Procedure Calls and Application Events as additional IPC mechanisms. The latter is used in event-driven interaction scenarios. The Softnet mechanism of Access Control can be used to implement different levels of access to devices, and a mechanism called Service Status Detection provides clients with information about the connectivity status of remote devices. Softnet also provides a convenient solution for managing devices, clients, user permissions, and shared access to devices with other individuals/organizations. The latter allows owners to establish user-to-user or business-to-customer relationships. Using Softnet, developers can focus on IoT application logic without concerning about networking issues.  

Softnet Free is licensed under Apache License, Version 2.0. You can use, modify and distribute the server software and endpoint libraries without any restrictions. We’ll be glad if you participate in the further development and improvement of the project.

As of June 2023, the [Softnet endpoint library](https://github.com/Softnet-Free/softnet-java/) is available in Java SE 1.7. It works on Linux platforms, Raspbian, Android 5.0 and later versions. The endpoint libraries for other platforms are under development. First of all, we focus on FreeRTOS, ChibiOS/RT and other RTOS platforms widely used in industrial microcontrollers such as STM32, PIC32, EFR32, Infineon XMC, TI SimpleLink, ESP32, etc.

If you want to know more about the Softnet platform, the following sources will be helpful:

* [Softnet Programming Model (Java)](https://softnet-free.github.io/softnet-java/) / This guide describes the process of developing IoT applications using Softnet Java Library;
* [The Developer Guide to Softnet ASN.1 Codec (Java)](https://softnet-free.github.io/asn1codec-java/) / This guide provides the specification for the API of Softnet ASN.1 Codec (Java). As an option, Softnet allows you to use the ASN.1 DER format to transfer data over a network, although you can use any other format, such as JSON;


<!--

**Here are some ideas to get you started:**

🙋‍♀️ A short introduction - what is your organization all about?
🌈 Contribution guidelines - how can the community get involved?
👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
🍿 Fun facts - what does your team eat for breakfast?
🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
-->
