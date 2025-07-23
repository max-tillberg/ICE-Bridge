# ICEBridge

![This is an image](https://github.com/maxtillberg/ICEBridge/blob/main/icebridge.png)

[Blender](https://www.blender.org/) or [grasshopper](https://www.grasshopper3d.com/) plugin to send/get BIM-data like IFC to and from [IDA ICE](https://www.equa.se/en/ida-ice).

## Requirements

To run this plugin, you need [Blender](https://www.blender.org/) or [Rhino](https://www.rhino3d.com/). I recommend installing [Speckle](https://speckle.systems/), [Bonsai](https://extensions.blender.org/add-ons/bonsai/) and/or [dotBIM](https://dotbim.net/) as well. It also helps if you have access to Revit and/or ArchiCAD, at least demo versions. To import the data you need [IDA ICE](https://www.equa.se/en/ida-ice).

## Installation

### Blender

Download and install [ICEBridge.zip](https://github.com/max-tillberg/ICE-Bridge/blob/main/ICEBridge.zip) as a normal Blender plugins. Instructions can be found [here](https://docs.blender.org/manual/en/latest/editors/preferences/addons.html)

### Rhino/grasshopper

This is still under development and will be delivered by request.

### IDA ICE 5

ICEBridge 2 requires IDA ICE 5.0 or later, preferable IDA ICE 5.2. ICEBridge for IDA ICE 4.8 can be found at https://github.com/maxtillberg/ICEBridge

![This is an image](https://github.com/maxtillberg/ICEBridge/blob/main/ICEBridge.png)

## Features
  
1. Send CAD objects to IDA ICE to be used as geometrical input, for example shading objects, building bodies, thermal zones, IDA ICE Ifc objects (walls, windows, doors, slabs and spaces), windows, openings and more. Objects can be stored as CAD objects or CAD geometries depending on import preferences IDA ICE. CAD geometries are separated by color (3DS) or optionally object (OBJ).
2. Read data from IDA ICE, for example zone geometry, zone result and field data through VTK. Data can be exported to Speckle.
3. Post process IDA ICE field data, for example mean and median values.
4. Send bitmaps to IDA ICE, for example field data and text strings like zone name.
5. Visualize occupants in 3D for CFD analysis.
6. Visualize sun path and sky dome with data if available

## Limitations
  
This is a proof of concept, not an official product by EQUA Simulation AB. There will be bugs and limitations.

## Input

ICEBridge works well with Bonsai and Speckle but any valid geometry will work. VTK must by ASCII.

## News

- 2025-07-21: Version 2.1 Zone geometry import, occupant 3D import, fast delete, faster VTK import, bug fixes.
- 2025-07-15: Version 2.0 Support for IDA ICE 5.2, most features removed since they have been implemented in IDA ICE 5.2, fewer dependencis, bitmap export, VTK import.
  
## Notes

- Open IDA ICE with the intended model before running ICEBridge, use unpacked formats so ICEBridge can access files and preferable use custom simulations for postprocessing.
- The 3D import can be quite slow and uses a lot of memory, therefore it can be a good idea to export/import larger buildings in parts, for example each floor.
- Do not import too large shading external objects since this will affect shading calculations. Try to simplify external objects if possible.
- For best performance, use fixed output of 0.5 hours and use custom simulation in IDA ICE.
