# What is OSI Model.

The OSI model is a conceptual framework that explains how data moves from one device to another over a network using seven logical layers, from physical transmission (cables, signals) upto user-facing application (like browsers or email clients). It is defined by ISO (International Standard Organization) to standardize how different devices communicate over networks. Each layer has a specific role and interacts only with the layer directly above or below it, which make complex networking easier to understand and design. The model is used to standardize communication so devices and softwares from different vendors can intercoperate instead of being to one proprietary design.

## Layers of OSI Model:

<img src="https://cdn.services-k8s.prod.aws.htb.systems/content/modules/289/network_concepts/OSI.png">

### Layer 1 - Physical Layer.

- This is the lowest layer of the OSI Model.
- It is responsible for the actual physical connection between the devices.
- The physical layer contains information in form of bits.

<img src="https://media.geeksforgeeks.org/wp-content/uploads/20241015103017414021/physical-layer.png">

- Its role is to to transfer individual bits from one node to next.
- When recieving data this layer will get the signal recieved and convert it into 0's and 1's and send them to data link layer, which will put the frame back together.

