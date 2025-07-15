# ICEBridge

![This is an image](https://github.com/maxtillberg/ICEBridge/blob/main/icebridge.png)

[Blender](https://www.blender.org/) or [grasshopper](https://www.grasshopper3d.com/) plugin to send/get BIM-data like IFC to and from [IDA ICE](https://www.equa.se/en/ida-ice).

## Requirements

To run this plugin, you need [Blender](https://www.blender.org/) and [BlenderBIM](https://blenderbim.org/) or [Rhino](https://www.rhino3d.com/). I recommend installing [Speckle](https://speckle.systems/), [Bonsai](https://extensions.blender.org/add-ons/bonsai/) and [dotBIM](https://dotbim.net/) as well. It also helps if you have access to Revit and/or ArchiCAD, at least demo versions. To import the data you need [IDA ICE](https://www.equa.se/en/ida-ice).

## Installation

### Blender

Download and install [ICEBridge.zip](https://github.com/max-tillberg/ICE-Bridge/blob/main/ICEBridge.zip) as a normal Blender plugins. Instructions can be found [here](https://docs.blender.org/manual/en/latest/editors/preferences/addons.html)

### Rhino/grasshopper

This is still under development and will be delivered by request.

### IDA ICE 5.2

ICE Bridge 2.0 requires IDA ICE 5.2 or later. ICE Bridge for IDA ICE 4.8 can be found at https://github.com/maxtillberg/ICEBridge

![This is an image](https://github.com/maxtillberg/ICEBridge/blob/main/ICEBridge.png)

## Usage
  
1. Create or import BIM- or CAD-data to Blender using BlenderBIM, Speckle, DOTBIM or CAD data as OBJ or DXF. 
2. Make sure that the data is valid. Zones and building bodies must be made up of closed volumes constructed out of planar surfaces or planar surfaces that can be extruded into volumes. Each mesh will create a separate zone or building body. Windows and doors works best if they are planar. Each mesh will create a separate window or door.
3. Select objects of one type with similar properties, for example zones. Supported objects are building bodies, zones, windows, doors and external (shading) objects.
4. Select the corresponding object type in ICEBridge, path and press "Export to IDA ICE". This will generate a script file and optionaly geometry files in the selected folder path. Exporting the same object type twice will overwrite the script file and geometries with the same name.

## Limitations
  
This is a proof of concept, not an official product by Equa Simulation AB. There will be bugs and limitations.

## Input

ICEBridge works well with Bonsai and Speckle but any valid geometry will work.

## News
- 2025-07-15: Version 2.0 Most features removed since they have been implemented in IDA ICE 5.2. Fewer dependencis.

## Notes
  
- The 3D import can be quite slow, therefore it can be a good idea to export/import larger buildings in parts, for example each floor.
- Importing without geometry will make zones non editable in IDA ICE and building bodies are more often non editable.
- Coplanar surfaces will not be merged automatically  if import without geometry is used.
- Building bodies can be created in Revit by deleting room bounding walls, floors and ceilings.
- Spaces can be created from any closed volume, for example Revit rooms or spaces or IFCSpaces.
- Building bodies and zones should if possible be created as objects that can be created in IDA ICE to be editable.
- Building bodies can be edited in IDA ICE if needed.
- External objects with similar properties are merged into one mesh to avoid too many objects.
- Do not import too large shading external objects since this will affect shading calculations. Try to simplify external objects if possible.
