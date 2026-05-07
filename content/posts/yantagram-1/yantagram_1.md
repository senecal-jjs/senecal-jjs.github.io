---
title: "A Decentralized Local-First Chat App"
author: "Jacob Senecal"
date: "2026-04-29"
summary: "How to architect an encrypted, decentralized, local-first chat application."
description: "A decentralized, local-first chat application."
toc: false
readTime: true
autonumber: true
math: true
tags: ["crypto", "mobile", "react native", "decentralized", "bluetooth"]
showTags: false
hideBackToTop: false
fediverse: "@username@instance.url"
---

For the past several months I've been developing a local-first, decentralized, end-to-end encrypted messaging app. I've dubbed this application "Yantagram", after the elvish "yanta" meaning "bridge", and the latin root "gram", meaning "letter".

There are many chat applications out in the world, so it is natural to ask the question, "Why?". My main concern has been providing a means of communication that is naturally resistant to centralized control and puts a user in charge of their own identity. I was inspired by similar applications, like BitChat (a decentralized, peer-to-peer bluetooth mesh), but I felt like the user interface wasn't similar enough to 
mainstream applications like iMessage to be fully user friendly. For example, BitChat doesn't support private group chats.

Yantagram relies on no central servers, a user's identity lives on their device, and it works fully offline, reconciling state with other users when back online. Yantagram can remain functional during internet outages, power disruptions, or natural disasters. 

## Local-First

A local-first application is software that stores data primarily on the user's local device (laptop, phone) rather than a remote server, enabling instant, offline-capable, and secure experiences. This is in contrast to iMessage for example, where backups may be stored remotely in Apple's servers.  

In Yantagram, all data, messages, identity, settings, etc. are stored only on the user's device. This inherently eliminates the need to trust that a third party company is managing your data responsibly. There are some downsides to a local-first application. If a user deletes Yantagram from their device,
there are no backups stored in a remote server that can be used to restore user state, if the application
is ever re-installed in the future. 

## Decentralized 

A decentralized application is one in which there are no central servers coordinating application authority, state, or functionality. A decentralized system is censorship resistant by default. When there is no single point of control, it becomes much more difficult to control or shut down the application.

In Yantagram there are no central servers required to create a functioning network. Devices can communicate peer-to-peer via a bluetooth mesh network, or via dumb, stateless, relay servers that can be stood up quickly by those with a small amount of technical knowledge. 

## Bluetooth Mesh Support

Devices with Yantagram installed connect to one another using Bluetooth, and act as both client and server in a distributed mesh network. A mesh network consists of multiple interconnected nodes relaying messages to one another. This is in contrast to a traditional network in which devices send information to a central node/server which then distributes information to other peripheral nodes.

The bluetooth mesh is a pillar in Yantagram's decentralized model, that allows the network to continue functioning in the absence of an internet connection.

## End-to-End Encryption
