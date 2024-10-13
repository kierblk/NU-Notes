# Chapter 1

Note: These notes are not based on class "lectures". I simply cannot follow the official instructor.
However, the author of the textbook has lectures freely available on YouTube. Given that the course
uses the official slides that were prepared by the textbook author, I am confident the lecturte
covers the same information.

## Chapter 1 - Introduction

- [Slides](/CS-5700-Networking-Fundamentals/Lectures/Chapter-1-v8.2.pdf)
- [Additional Materials](https://gaia.cs.umass.edu/kurose_ross/videos/1/)

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
- Provides service options, analogous to the postal service

**What is a Protocol -->**

Analogous to many "Human protocols":

- "What time is it?"
- "I have a question.."
- Introductions

These are "rules" that dictate an interaction. Rules for specific messages sent or specific actions taken when a message is received or other events. 

Network protocols are computers devices, rather than humans. However, these protocols govern all communication activity on the internet. 

*Protocols define the format, order of messages sent and received among network entitites, and actions taken on msg transmission and receipt.*

### 1.1 Knowledge Check

1. Which of the following descriptions below correspond to a "nuts-and-bolts" view of the Internet? Select one or more of the answers below that are correct. [Hint: more than one of answers below are correct].

- [ ] A place I go for information, entertainment, and to communicate with people.
- [ ] A platform for building network applications.
- [x] A collection of hardware and software components executing protocols that define the format and the order of messages exchanged between two or more communicating entities, as well as the actions taken on the transmission and/or receipt of a message or other event.
- [x] A collection of billions of computing devices, and packet switches interconnected by links.
- [x] A "network of networks".

2. Which of the following descriptions below correspond to a "services" view of the Internet? Select one or more of the answers below below that are correct below that are correct.  [Hint: more than one of answers below are correct].

- [x] A platform for building network applications.
- [ ] A collection of hardware and software components executing protocols that define the format and the order of messages exchanged between two or more communicating entities, as well as the actions taken on the transmission and/or receipt of a message or other event.
- [x] A place I go for information, entertainment, and to communicate with people.
- [ ] A "network of networks".
- [ ] A collection of billions of computing devices, and packet switches interconnected by links.

3. Which of the following human scenarios involve a protocol (recall: "Protocols define the format, order of messages sent and received among network entities, and actions taken on message transmission, receipt")? Select one or more answers below that are correct. Hint: more than one of answers below are correct.

- [ ] A person sleeping.
- [x] A student raiding his/her/their hand to as a really insightful question, followed by the teacher acknowledging the student, listening carefully to the question, and respeonding with a clear, insightful answer. And then thanking the student for the question, since teachers LOVE to get questions.
- [x] Two people introducing themselves to each other.
- [ ] A person reading a book.
- [x] One person asking, and getting, the time to/from another person.

### 1.2 The Network Edge

- Access networks, physical media
- [Online lecture (15:56)](https://www.youtube.com/watch?v=k8NmM-hImBU)

The big question here is **HOW** to connect end systems to edge router.
There are three types of access networks that connect end systems to edge routers:

1. Residential access networks
2. Institutional access networks (school, company)
3. Mobile access networks (WiFi, 4G/5G)

What to look for:

- Transmission rate (bits per second) -- aka 'how fast is the network' -- of the access network?
- Do what degree do uses share this network among other users?

#### Access Networks

Will be reviewed in greater detail in chapter 6

**Cable**
![](/CS-5700-Networking-Fundamentals/Lectures/1-14-15.png)

**DSL**
![](/CS-5700-Networking-Fundamentals/Lectures/1-16.png)

**Home**
![](/CS-5700-Networking-Fundamentals/Lectures/1-17.png)

**Wireless**
![](/CS-5700-Networking-Fundamentals/Lectures/1-18.png)

**Enterprise**
![](/CS-5700-Networking-Fundamentals/Lectures/1-19.png)

**Data Centers**
![](/CS-5700-Networking-Fundamentals/Lectures/1-20.png)

#### Hosts

![](/CS-5700-Networking-Fundamentals/Lectures/1-21.png)

#### Physical Media

Some basic facts about physical media...

- **bit**: propagates between transmitter/receiver pairs
- **physical link**: what lies between transmitter and receiver
- **guided media**: signals propagate in solid medida: copper, fiber, coax
- **unguided media**: signals propagate freely: radio

1. Twisted Pair (TP): two insulated copper wires

- Category 5: 100 Mbps, 1 Gbps Ethernet
- Category 6: 10 Gbps Ethernet

2. Coaxial Cable: two concentric copper conductors

- bidirectional
- broadband
  - multiple frequency channels on cable
  - 100's Mbps per channel

3. Fiber Optic Cable: glass fiber carrying light pulses, each pulse a bit

- high-speed operation
  - high-speed point-to-point transmission (10s - 100s Gbps)
- low error rate
  - repeaters spaced far apart
  - immune to elctromagnetic noise

4. Wireless Radio

- signal carried in various "bands" in electromagnetic spectrum
- no physical "wire"
- broadcast, "half-duplex" (sender to receiver)
- propagation environment effects
  - reflection
  - obstruction by objects
  - interference / noise

**Radio Types**

- Wireless LAN (WiFi)
- Wide-area (4G/5G)
- Bluetooth: cable replacement
  - short distances, limited raates
- Terrestrial Microwave
  - point-to-point, 45 Mbps channels
- Satellite
  - up to <100 Mbps (Starlink) download
  - 270 msec ent-to-end delay (geostationary)

### 1.2 Knowledge Check

1. Match the Following:
`Ethernet`, `802.11 WiFi`, `Cable Access Network`, `Digital Subscriber Line`, `4G cellular LTE`

    A. Wired. Up to 10’s to 100’s of Mbps downstream per user. --> `Cable Access Network`

    B. Wired. Up to 100's Gbps per link. --> `Ethernet`

    C. Wired. Up to 10’s of Mbps downstream per user. --> `Digital Subscriber Line`

    D. Wireless. Up to 10’s Mbps per device. --> `4G Cellular LTE`

    E. Wired. Up to 1 Tbps per link.

    F. Wireless. 10’s to 100’s of Mbps per device. --> `802.11 WiFi`

    G. Wireless, up to 10's Kbps per device.

2. Which of the following physical layer technologies has the highest transmission rate and lowest bit error rate in practice?

    A. Twisted pair (e.g., CAT5, CAT6)

    B. 802.11 WiFi Channel

    C. Fiber optic cable --> `THIS one!`

    D. Coaxial cable

    E. 4G/5G cellular

    F. Satellite channel