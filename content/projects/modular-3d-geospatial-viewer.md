+++
title = "Modular 3D Geospatial Viewer"
description = "A modular web platform for visualising and editing point clouds, BIM models and geospatial data."
category = "Academic"
weight = 100
showDate = false
toc = false
+++
Developed as my BSc thesis project, this is a modular 3D mapping platform with an independent Vite-packaged core library and React user interface.

[Read the BSc thesis (PDF)](https://repozitorij.uni-lj.si/Dokument.php?id=213249&lang=slv)

- Combined point clouds, GeoJSON geometry, IFC/BIM models, 3D Tiles and georeferenced imagery in one layered viewer using Three.js and specialised libraries.
- Developed a performance-focused Three.js-based renderer for GeoJSON data, covering all geometry types.
- Developed drawing and editing tools, cursor snapping across data types, project saving and loading, layer controls, an OpenLayers minimap and custom 3D clipping tools.

## Live demo
Click the link below to open the live demo. Note that this particular version of the viewer is an experimental snapshot I built for a demonstration, so it includes some extra features (such as 3D tiles support, a minimap and model clipping), but some features are broken as a result.

{{< geom3d-demo >}}
