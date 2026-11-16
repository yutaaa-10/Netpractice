*This project has been created as part of the 42 curriculum by yukurosa.*

# NetPractice

## Description

NetPractice is a project for learning the fundamentals of computer networking by configuring networks in a web-based simulation environment.

It covers network segmentation using IP addresses and subnet masks, the roles of switches and routers, network interface configuration, and the use of routing tables to control packet forwarding.

The goal is to configure IP addresses and routes to meet the communication requirements of all 10 levels and understand how packets travel between different networks.

## Instructions

### Installation and Launch

Python 3, Bash, and a web browser are required. No compilation is needed.

Download the archive from the 42 project page and place it in a working directory of your choice. If the archive is named net_practice.1.10.tgz, run the following commands in a terminal. Adjust the filename if your archive has a different name.

```bash
# Extract the archive
tar -xf net_practice.1.10.tgz

# Enter the extracted directory
cd net_practice

# Launch NetPractice
./run.sh
```

To use the environment already extracted in this repository, run `cd net_practice` followed by `./run.sh` from the repository root.

`run.sh` starts a local web server and opens the training interface in your browser.
If it does not start correctly, run the following command inside the `net_practice` directory and open `http://localhost:49242` in your browser.

```bash
python3 -m http.server 49242
```

If the port is already in use, choose a different port and update the browser URL accordingly. To stop the server, press `Ctrl+C` in the terminal where it is running.

### Starting the Training

When creating configurations for submission, enter your 42 login on the start screen.
Complete all 10 levels using the personal configuration associated with your login. To practice with random configurations, you can also use the `evaluation` tab.

### Exporting Configuration Files

At each level, adjust the IP addresses, subnet masks, routing tables, and other editable fields to meet the communication requirements shown at the top of the page. If communication fails, check the logs at the bottom of the page to identify the cause.

Once the configuration is complete, save it as follows:

1. Click Check again and confirm that all communication goals show OK.
2. Click Get my config to export the configuration file before moving to the next level.
3. Save the exported file at the root of your submission Git repository with a name that identifies its level, such as level1.json.
4. Click Next level and repeat these steps for all 10 levels.

### Submission

Complete all 10 levels and place the configuration files exported using Get my config **at the root of your submission Git repository: one file per level, for a total of 10 files**. Place README.md in the same location.

```text
.
├── README.md
├── level1.json
├── level2.json
├── level3.json
├── level4.json
├── level5.json
├── level6.json
├── level7.json
├── level8.json
├── level9.json
└── level10.json
```


## Resources

### References

The following resources explain the networking fundamentals covered in this project. The linked articles are in Japanese.

- [What Is a Network? How It Works, Network Types, and Setup](https://www.qtpro.jp/blog/network/14.html)
- [What Is TCP/IP? An Introduction to Network Communication](https://www.hokuyo-aut.co.jp/products/data.php?id=487)
- [IP Address and Subnet Mask Basics](https://www.secuavail.com/kb/practical-post/ip-address-subnet-mask/)
- [A Complete Guide to CIDR: CIDR Notation and IP Addresses](https://envader.plus/article/52)
- [Differences Between Layer 2 Switches, Layer 3 Switches, and Routers](https://qiita.com/FScom_Japan/items/a59e3a6065ee787cf33a)
- [What Is the OSI Model?](https://www.cloudflare.com/ja-jp/learning/ddos/glossary/open-systems-interconnection-model-osi/)

### Networking Concepts Studied

This project covers the following networking concepts:

* TCP/IP addressing: Using IP addresses to identify network interfaces and specify communication destinations in a TCP/IP network. This project uses IPv4.
* Subnet masks and CIDR: Defining network boundaries by separating the network and host portions of an IP address.
* Default gateway: The router to which packets are forwarded when no more specific route matches the destination. Its IP address must be reachable on a directly connected network.
* Routers: Network devices that forward packets between different networks.
* Switches: Network devices that primarily connect devices within the same LAN and forward frames based on MAC addresses.
* Routing tables: Information used to determine where packets should be forwarded based on their destination network.
* OSI model: A conceptual model that divides network communication into seven layers: physical, data link, network, transport, session, presentation, and application. A typical Layer 2 switch operates mainly at Layer 2, while a router operates at Layer 3.

### Use of AI

AI was primarily used for the following tasks:

* Understanding basic concepts such as IP addresses, subnet masks, and CIDR.
* Clarifying the roles of routers, switches, default gateways, and routing tables.
* Understanding the causes of communication errors and how packets travel from source to destination.
* Improving and translating the README, checking it against the project requirements, and adding reference links.
