---
layout: post
title: Linux Networking
category: Linux
tags: linux
keywords: null
description: null
published: true
---


## 網絡層（Network Layers）
  
### OSI七層

當我們提到Protocol Layers大部分人都會想起OSI七層協定（Application, Presentation, Session, Transport, Network, Data Link and Physical）。但我在這篇文章主耍討論Layer 2 和 Layers 3。因為這兩個Layers令我們便認識網絡。你或者會常聽到Administrator講"this is a layer 2 device" 或 "this is a layer 3 broadcast"。看完這篇文章你將會明白他們在講什麼。
### DoD四層（four DoD layers）

DoD Model(在台灣比較多人叫做TCP/IP Model)，這個Model只是跟OSI Model有個對映而且。如以下圖表。  

![alt text](https://github.com/johnkwong/johnkwong.github.io/blob/master/_posts/Linux/networklayers.png "networklayers")

### 簡短介紹Physical Layer

第一層是Physical Layer，大多我們提到的那些「電壓、電子信號和連接器」也是屬這一屠。而Repeater和hub就屬這個部分。你可以透過網絡使用軟件去看他們。而Hub就分為Passive hubs 和Active hubs ，前者只是把所有的Port連接起來，而後者還有Repeater的功用。   在一層的網絡技術例如有csma/cd或token ring 。    
### 簡短介紹Data link layer

第二層的Data link layer與Frames有關。而Frame有一個crc (cyclic redundancy check).這層的設備有bridges和switches。他們都可以認證到Mac address。我們會用arp & ifocnfig這兩個指令暸解這層。  
### 簡短介紹network layer

第三層的network layer與ip packets有關。這層會給每台Host一個unique 32-bit ip address。但這層有很多protocol。可以查看/etc/protocols。  
這層的Device有routers 或 layer 3 switches, 而Devices 有一個ip address。  
### 簡短介紹 transport laye

我在之後會在TCP/UDP Protocols章節才討論。  
### Layers 5, 6 and 7

之後再討論  

