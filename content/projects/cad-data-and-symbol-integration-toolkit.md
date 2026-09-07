+++
title = "CAD Data and Symbol Integration Toolkit"
description = "A two-way CAD resource conversion toolchain and GeoJSON import plug-in."
category = "Professional"
weight = 60
showDate = false
toc = false
+++
A company-wide C#/.NET toolchain for maintaining shared CAD symbols and importing geospatial business data into AutoCAD.

- Built a two-way conversion process that decompiled ten separate CAD symbol and line-style files into a canonical GeoJSON library, then recompiled it into two unified CAD resource files.
- Preserved drawing behaviour throughout the conversion, including scaling, compound line patterns, referenced symbols and polygon fills, while establishing one maintainable source of truth.
- Developed an AutoCAD plug-in that imports business-system GeoJSON as correctly layered and styled 2D/3D points, lines, polygons, labels and reusable blocks.
- Packaged shared symbol and line-style resources with drawings so that they render correctly without requiring separate company-file installation.