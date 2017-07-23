---
layout: post
title:  New release - 0.7-beta
author: Casey & Hans
date:   2017-07-23 00:00:01
images: images/space0-7.png
excerpt:
  125 commits, 61 files changed, 3000 lines of code edited, and countless empty bottles of rum were spent but we hope you like the changes. 0.7-beta is finally here! A larger release than what we aimed for, but a milestone for the Hashview project.
categories: Releases
---
## Major Changes at a Glance

1) Distributed cracking!  
2) Smart wordlists  
3) Hashview Hub  
4) More analytics  
5) Additional Support for more hashes  
 

#### Distributed Cracking
We had to make significant changes to handle distributed queuing which took us a bit longer. We have an API for remote agents and distributed support is painless.

<img src="/images/distributed-hashview.png" alt="agents" style="width: 600px;"/>

##### Setup Agents
Install Hashview as normal, install Hashview Agent on a remote box and join it to the cluster via API. Checkout the <a href="https://github.com/hashview/hashview-agent" target="_blank">Hashview Agent</a> for more details.

#### Smart Wordlists
In an effort to improve your cracking results, we've taken our first stab at creating dynamic wordlists. These wordlists are a unique set of all plaintext words generated in hashview, both in the database, as well as for all wordlists. This wordlist is constantly updated and is supported like traditional wordlists (i.e. you can use rules with them) (detailed blog on how this works to follow)

#### Hashview hub
Hashview Hub is a free optional service that allows you to search our cloud based service for matching hashes that have already been cracked. As of this blog post Hub contains over 350 million hashes. To enable this service, look under the Manage -> Global Settings -> Hashview Hub. For your privacy, Hashview will only upload cracked hashes to the hub service if YOU want, and will NEVER send usernames, customer names, or any other identifiable information.

#### More Analytics!
We keep adding more popular analytics. This release we have the following:

##### Composition breakdown  
how many passwords meet complexity requirements  

<img src="/images/comp-breakdown.png" alt="compb" style="width: 600px;"/>

##### Composition details  
what are the most frequently used masks  

<img src="/images/comp-details.png" alt="compd" style="width: 600px;"/>

##### Weak passwords  
a list accounts/hashes containing extremely weak passwords  

<img src="/images/weakpasswords.png" alt="weakpass" style="width: 600px;"/>


#### Additional Supported Hash Types
The following hash types have been added
md5($salt.$pass.$salt)  
MySQL4.1/MySQL5  
sha1($salt.sha1($pass))  
sha1($salt.$pass.$salt)  
phppass  
WordPress(MD5)  
Joomla (MD5)  
Phppass  
phpBB3 (MD5)  
Juniper IVE  
Blake2b-512  
SHA-224  
SHA-256  
sha256($pass.$salt)  
sha256($salt.$pass)  
sha256(unicode($pass).$salt)  
Sha256   
salt.unicode($pass))  
HMAC-SHA256 (key = $pass)  
HMAC-SHA256 (key = $salt)  
SHA-3 (Keccak)  
GOST R 34.11-94  
Apache $apr1 MD5  
Md5apr1  
MD5(ARP)  
SHA-512  
sha512($pass.$salt)  
sha512($salt.$pass)  
sha512(unicode($pass).$salt)  
Sha512  
alt.unicode($pass))  
HMAC-SHA512 (key = $pass)  
HMAC-SHA512 (key = $salt)  
Whirlpool  
Cisco-PIX MD5   
Cisco-ASA MD5   
iSCSI CHAP authentication  
MD5(CHAP)   
Cisco-IOS type 4 (SHA256)   
Samsung Android Password/PIN   
AIX {smd5}   
AIX sha256}  
AIX {ssha512}  
AIX {ssha1}  
FortiGate (FortiOS)  
OSX v10.8+ (PBKDF2-SHA512)   
Grub 2   
IPMI2 RAKP HMAC-SHA1   
Drupal7  
Sybase ASE  
Citrix NetScaler  
DNSSEC (NSEC3)  
WBB3 (Woltlab Burning Board)  
+Lotus Notes/Domino 5  
script  
Lotus Notes/Domino 8  

