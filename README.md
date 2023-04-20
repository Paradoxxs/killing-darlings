# ICS forensics

industrial control system (ICS), is computer system that is used to monitor and control industrial processes, such as those in manufacturing, power generation, and transportation. ICS includes a combination of hardware and software, and communication networks, for the collecting of data from sensors and actuators, processing of data, and finally make control decisions based on the data. ICS is critical for the safe and efficient operation of many industries.

These systems are typically highly complex, with multiple components and interdependencies. This can make it difficult for investigators to understand the relationships between different parts of the system, and to identify the specific evidence that is relevant to their investigation. Which is why it critical to work together with the engineers onsite.

### Challenges of ICS/OT forensics

Examiner should be aware it likely not possible to take down the system to perform forensics imaging, or perform any changes to the system, as it brings the whole operation at risk. Your job is most likely to analysis the state of the environment and if there are any risk to the operation, if deem there is no risk it will most likely first be handle at the next maintenance window, which could be months or years from when it was discovered.

Another is the difficulty of accessing and analyzing data from these systems. These systems are often isolated from other networks, making it difficult for investigators to collect and analyze the data.

### Components

It critical for an examiner to understand the different components that makes up ICS and their function, to know which components should be part of the investigation and which should not.\
The main components of an OT and ICS system typically include sensors and actuators, control systems and controllers, communication networks and protocols, and human-machine interfaces (HMIs).

Sensors and actuators are the physical components of an OT and ICS system that are responsible for collecting data from the environment and controlling the operation of the system. Sensors are used to measure various physical parameters, such as temperature, pressure, and flow rate, while actuators are used to control the operation of the system, such as by opening or closing valves or adjusting the speed of motors.

Control systems and controllers are the software and hardware components of an OT and ICS system that are responsible for interpreting the data collected by the sensors and actuators, and determining the appropriate actions to take based on that data. Control systems is a collection of algorithms and rules that are used to make decisions about the operation of the system, while controllers are responsible for implementing those decisions in the physical world.

Communication networks and protocols are the infrastructure and standards that are used to connect the various components of an OT and ICS system, and to enable them to communicate with each other. This can include both wired and wireless networks, as well as a range of different protocols and standards that are used to transmit data and control signals between the different components of the system. The protocol used in ICS are not the same used in traditional one of the commonly used is modbus.

Human-machine interfaces (HMIs) are used by human operators to monitor and control the operation of an OT and ICS system. HMIs can include graphical displays, buttons, switches, and other controls that allow operators to view the status of the system and to make changes to its operation.

What can be interesting from an forensics perspective, are the general-purpose computer which are frequently used as data historian, engineering workstation and supervisory function such as human machine interface (HMI). Allowing you to use the standard forensics procedure.\
The main difference between standard forensics, that you should be more application aware as they are frequently the location of interest and have their own logs, for what occurred within the application.

### Investigation

One common mistake in performing forensic on ICS is to concentrate on the well-understood operating system, as the have forensics specialist understanding ICS is rare. However, it is important to also consider field devices such as PLC.

In order to perform successful forensics examination of the controls you need a baseline of system.\
This allow an examiner to compare the current state with an previous know-good state, without, it can become difficult to understand the changes that have happened.

This should include hardware configuration, this include schematics and wiring schema.\
The PLC configuration.\
For the PLC a full copy of all the ladder logic program, of the last know-good state should be available for comparison.

When it comes to network, document the network architecture including address, settings such as subnet mask and default gateway. what port are listening, on which devices.

The goal is to sit together with the ICS engineer when it comes to the special equipment and go through any chances and identify if they are malicious in nature.

ICS forensics is a complex and evolving field, as ICS environments are typically unique and can include a wide variety of hardware and software components. Additionally, ICS networks are often isolated from the internet and other corporate networks, which can make it challenging to gather digital evidence.
