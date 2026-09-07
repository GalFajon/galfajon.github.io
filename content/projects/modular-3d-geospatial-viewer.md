+++
title = "Modular 3D Geospatial Viewer"
description = "A modular web platform for visualising and editing point clouds, BIM models and geospatial data."
category = "Academic"
weight = 10
showDate = false
toc = false
+++
Developed as my BSc thesis project, this is a modular 3D mapping platform whose Vite-packaged core library can be used independently of its React interface. Applications can include only the interface features they need.

[Read the BSc thesis (PDF)](https://repozitorij.uni-lj.si/Dokument.php?id=213249&lang=slv)

- Combined point clouds, GeoJSON geometry, IFC/BIM models, 3D Tiles and georeferenced imagery in one layered viewer using the Three.js ecosystem.
- Developed a performance-focused GeoJSON renderer covering all geometry types and batching large point collections into efficient point-cloud representations.
- Added drawing and editing tools, snapping across data types, project saving and loading, layer controls, an OpenLayers minimap and custom 3D clipping tools.