+++
title = "Parking and Access Operations Platform"
description = "A full-stack platform for parking access, live camera feeds and barrier operations."
category = "Professional"
weight = 20
showDate = false
toc = false
+++
A deployed full-stack application for managing parking access, vehicle records, barriers and operational events.

- Built the application with React, TypeScript, Node.js and Vite.
- Integrated AxTraxNG access-control hardware through its REST API and modelled access points in PostgreSQL, mapping controller inputs and outputs to interface controls.
- Embedded live camera feeds through go2rtc and built an OpenLayers operations map that displays access-point locations and highlights incoming calls using a call-centre API.
- Designed a server-side event cache that prevents repeated upstream requests when multiple clients poll for updates.