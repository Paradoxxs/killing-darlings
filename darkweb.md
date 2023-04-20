# Darkweb

## Freenet

Freenet is a free and open-source software that allows users to browse the internet anonymously and securely. It is designed to protect users' privacy and freedom of expression by routing their internet traffic through a network of volunteer-operated nodes, which encrypts the data and makes it difficult for anyone to track the users' online activity or censor their content. Freenet is often used by activists, journalists, and others who need to protect their privacy and communicate securely.

Distribution of file sharing, small userbase

When content is uploaded, it is broken into pieces and distributed across the nodes, Uploading a file will provided a key, anyone that want to retrievere the information must provide the key.

Browsing freenet involves requesting files from the data store and viewing them locally, There can be a high latency with request for data because they have to be assembled from multiple source, The long your node is online and the more space you give it, the faster the speed will be because more data will be stored locally.

Modes

* Low security
  * Opennet connects to random peers, It less secure because you do not know who those peer are.
* High Security
  * Darknet mode will only connect to nodes that you have specified. It more secure because you know the node you are sharing data with.

Keys

* Content hash keys (CHK) : file
* Signed subspace keys (SSK) : web site
* Updatable subspace keys (USK) : version of sites
* Keyword signed keys (KSK)

Tool

* Freenetproject.org

## The invisible internet project (I2P)

The Invisible Internet Project, or I2P, is a free and open-source software for enabling anonymous communication. It is designed to protect users' privacy and security by routing their internet traffic through a network of volunteer-operated servers, which encrypts the data and hides the users' IP addresses. This makes it difficult for anyone to track the users' online activity or identify their location. I2P is often used by activists, journalists, and others who need to protect their online identity and communicate securely.

Anonymity and security for communications, Medium user base.

The main purpose of I2P is to protect communication from eavesdropping, monitoring and traffic analysis, This is done by using one way tunnel that are temporal tunnels.

Traffic flows from outbound tunnels across multiple hops to inbound tunnel, it is then consumed and rerouted or used.

* ![](https://remnote-user-data.s3.amazonaws.com/o39pzYPzzjUcKv4Ck7l3pCcC4agyRKl1f0q5IFnXfZhKT7ELpNNWhQeLk-o7E2-j0W0AQQk4CWtFd7ll0O8wLXirexL9AEe\_diqh9poQKI84EZc7aeRn5E7sddlFq4CW.png)

I2P uses a hosts.txt or Block file binary naming service for translation. Other users hosts files are periodically merged with yours. Users configure subscriptions to other hosts files or address books for regular mering. Thes actions increase the number of sites and nodes your computer knows.

Tools

* geti2p.net
