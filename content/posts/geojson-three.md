+++
date = '2026-11-11T12:00:00Z'
draft = false
title = 'GeoJSON Three is live'
tags = ['IT']
description = 'Reimplementing the GeoJSON viewer from my BSc thesis, with precise rendering at real-world coordinates.'
image = 'https://raw.githubusercontent.com/GalFajon/geojson-three/main/docs/site.jpg'
imageAlt = 'GeoJSON Three site plan demo showing geospatial features in a 3D scene'
+++

For my BSc thesis, I developed Geom3D, a modular 3D geospatial viewer that brings GeoJSON geometry together with point clouds and 3D models. One part of that work was a Three.js-based GeoJSON renderer. I have since revisited it and built [geojson-three](https://www.galfajon.dev/geojson-three/), an optimized reimplementation focused on rendering and editing GeoJSON at real-world coordinates.

GeoJSON Three is a standalone library for rendering and editing GeoJSON in Three.js. It uses float64 anchors and local vertex offsets to keep small features precise at large projected or geocentric coordinates. It supports styling, picking, extrusion and editable geometries, with demos for a site plan, large point sets and an interactive editor. You can [try the demos](https://www.galfajon.dev/geojson-three/) or explore the [source code on GitHub](https://github.com/GalFajon/geojson-three).

{{< figure src="https://raw.githubusercontent.com/GalFajon/geojson-three/main/docs/site.jpg" alt="GeoJSON Three site plan demo showing geospatial features in a 3D scene" caption="The GeoJSON Three site plan demo." >}}
