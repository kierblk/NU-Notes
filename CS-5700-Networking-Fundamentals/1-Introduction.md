# Chapter 1

Note: These notes are not based on class "lectures". I simply cannot follow the official instructor.
However, the author of the textbook has lectures freely available on YouTube. Given that the course
uses the official slides that were prepared by the textbook author, I am confident the lecturte
covers the same information.

## Chapter 1

- [Slides](/CS-5700-Networking-Fundamentals/Lectures/Chapter-1-v8.2.pdf)
- https://gaia.cs.umass.edu/kurose_ross/videos/1/

### 1.1 What is the Internet?

- Chapter goals; a nuts-and-bolts and a services description. What is a protocol?
- [Online Lecture (13:35)](https://www.youtube.com/watch?v=74sEFYBBRAY&t=1s)

**What is the Internet? -->**

"Nuts-and-Bolts" Description:

- Billions of connected computing devices (hosts) running network apps at the internet's edge
- Packet switches (routers and switches) forward packets -- chunks of data.
- Communication links such as fiber, copper, radio, and satellite, with a transmission rate (bandwidth)
- Networks which are a collection of devices, routers, and links managed by an organization
- A "network of networks" via interconnected ISPs
- Protocols are everywhere controlling the sending and receiving of messages (e.g. HTTP, TCP, IP, WiFi, 4G, Ethernet)

Services Description:

- The infrastructure that provides services to applications: Web streaming video, multimedia teleconferencing, email...
- Provides the programming interface to distributed applications: "hooks" allowing sending/receiving apps to "connect" to and use Internet transport service.
- Provides service optionas, analogous to the postal service

**What is a Protocol -->**

Analogous to many "Human protocols":

- "What time is it?"
- "I have a question.."
- Introductions

These are "rules" that dictate an interaction. Rules for specific messages sent or specific actions taken when a message is received or other events. 

Network protocols are computers devices, rather than humans. However, these protocols govern all communication activity on the internet. 

**Protocols define the format, order of messages sent and received among network entitites, and actions taken on msg transmission and receipt.**

### 1.2 The Network Edge

- Access networks, physical media
- [Online lecture (15:56)](https://www.youtube.com/watch?v=k8NmM-hImBU)

