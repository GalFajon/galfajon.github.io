+++
title = "Parking and Access Operations Platform"
description = "A full-stack platform for parking access, live camera feeds and barrier operations."
category = "Professional"
weight = 20
showDate = false
toc = false
+++
A deployed full-stack application for managing parking access, vehicle records, barriers and operational events.

- Built and deployed the application using React, TypeScript, Node.js and Vite.
- Integrated AxTraxNG access-control hardware through its REST API and modelled access points in PostgreSQL, mapping controller inputs and outputs to interface controls and connecting them to external metadata such as video streams and call-centre phone numbers.
- Embedded live camera feeds through go2rtc and built an OpenLayers operations map that displays access-point locations and highlights incoming calls using a call-centre API.
- Implemented a server-side cache for event data that prevents repeated upstream requests when multiple clients poll for updates.