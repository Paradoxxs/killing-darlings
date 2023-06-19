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



  ## Darkfeed Ransom

[Darkfeed Ransom](https://darkfeed.io/ransomwiki/) is a curated list of ransomware actor websites and a list of available decryptors for specific strains of ransomware.

By utilizing these threat intelligence tools and platforms, you can gather valuable information about potential threats, IOCs, and TTPs. Staying informed about the latest threats and using multiple sources of intelligence will help you make better-informed decisions when dealing with potential cyber risks.

<div style="page-break-after: always;"></div>


# Dark web

The dark web is a part of the internet that is not indexed by search engines and can only be accessed using special software like the Tor browser. It is a decentralized network of websites and online services that employ encryption and other technologies to protect user anonymity and the confidentiality of their activities. The dark web is often associated with illegal or nefarious activities, such as the sale of illegal goods and services, money laundering, and the distribution of stolen data and information. However, it is also used for legitimate purposes, like allowing journalists and activists to communicate securely and protect their privacy.

When discussing the dark web, most people are referring to the onion router, commonly known as Tor. Tor is free, open-source software that enables anonymous communication. It protects users' privacy and security by routing their internet traffic through a network of volunteer-operated servers, encrypting the data, and hiding users' IP addresses. This makes it difficult for anyone to track users' online activities or identify their locations. Tor is often used by journalists, activists, and others who need to protect their online identities and communicate securely.

<div style="text-align: center;">
  <img src=".gitbook/assets/tor.png" style="width: 80%; max-width: 80%;">
</div>

The main purpose of the onion routing project is to protect the route your data takes from your system to its destination and to defeat censorship, network blocking, and monitoring. The software chooses a path with a set of nodes (default is 3) and negotiates a virtual circuit through the network, in which each node knows only its predecessor and successor node. As traffic flows through the circuit, it is unwrapped by a symmetric key at each node, revealing the next node. The Tor project has published a list of all their exit nodes [Tor exit list](https://check.torproject.org/torbulkexitlist), and another option is [project metrics](https://metrics.torproject.org/exonerator.html), which can also identify if an IP address has been used as a Tor relay.


<div style="text-align: center;">
  <img src=".gitbook/assets/ExoneraTor.png" style="width: 80%; max-width: 80%;">
</div>

Caution when using Tor:

* Be careful with files downloaded from Tor, as there's a high chance they could be malicious
* Use HTTPS whenever possible
* Avoid using personal information
* Steer clear of internet sites requiring authentication from Tor
* Be aware of potential attacks against the browser and computer system
* Stay away from illegal material

I recommend setting the TOR browser to the safest setting, this will disable Javascript and autoplay on video.

### Search engines

Several services similar to Google focus on indexing Tor sites. No site has indexed the entire Tor network, so it's important to use multiple services for better coverage.

<div style="text-align: center;">
  <img src=".gitbook/assets/ahmia.png" style="width: 80%; max-width: 80%;">
</div>

Tor search engines:
- [AHMIA](https://ahmia.fi/)
- [Tordex](http://tordexu73joywapk2txdr54jed4imqledpcvcuf75qsas2gwdgksvnyd.onion/)
- [Haystak](http://haystak5njsmn2hqkewecpaxetahtwhsbsa64jom2k22z5afxhnpxfid.onion/)
- [Fresh onions](http://freshonifyfe4rmuh6qwpsexfhdrww7wnt5qmkoertwxmcuvm4woo4ad.onion/)
- [Onion link list](http://donionsixbjtiohce24abfgsffo2l4tk26qx464zylumgejukfq2vead.onion/onions.php)
- [Onion live](https://onion.live/)

### Onionscan

[Onion Scan](https://github.com/s-rah/onionscan) is a dark web investigation tool designed to help researchers and investigators monitor and track Tor sites and identify security issues within their services, such as misconfigurations.

Verbose output from the scanning:

```
onionscan --verbose site.onion
```

You can also create a JSON report:

```
onionscan --jsonReport site.onion
```

### TorBot

[Torbot](https://github.com/DedSecInside/TorBot) is an onion web crawler.

### Onioff

[OniOFF](https://github.com/k4m4/onioff) is an onion URL inspector.

To inspect a list of onion sites and output the results to a txt file, use:

```
python onioff.py -f onions.txt -o report.txt
```
