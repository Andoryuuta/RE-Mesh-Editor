![REMeshEditorTitle](https://github.com/NSACloud/RE-Mesh-Editor/assets/46909075/156d0b53-ff4f-43db-9a3d-9e0cbd71326e)

**BETA RELEASE, THERE MAY BE BUGS**

This addon allows for importing and exporting of RE Engine mesh and mdf2 (material) files natively in Blender.
### [Download RE Mesh Editor](https://github.com/NSACloud/RE-Mesh-Editor/archive/refs/heads/main.zip)

![MeshEditorPreview](https://github.com/NSACloud/RE-Mesh-Editor/assets/46909075/e488c6d5-6e15-4dff-9ae2-815d0a1bb142)

## Features
 - Allows for importing and exporting of RE Engine mesh files.
 - Allows for importing and exporting of RE Engine mdf2 (material) files.
 - MDF material editing from within Blender.
 - Preset system that allows for presets of materials to be saved and shared.
 - Supports LOD (level of detail) import and export.
 - Texture conversion tools.
 - Collection based system that allows for export with multiple mesh files in a scene.
 - RE Toolbox batch export integration. Any files exported will be added to the RE Toolbox batch export list.
   
 ## Supported Games
 - **Devil May Cry 5**
 - **Resident Evil 2/3 Remake (Supports both RT and Non RT Versions)**
 - **Resident Evil 4 Remake**
 - **Resident Evil 7 Ray Tracing Version**
 - **Resident Evil 8**
 - **Monster Hunter Rise**
 - **Street Fighter 6**
 - **Dragon's Dogma 2**
 - **Kunitsu-Gami: Path of the Goddess**
 
Support for more games may be added in the future.

## Requirements
* [Blender 2.93 or higher](https://www.blender.org/download/)
* [RE Toolbox](https://github.com/NSACloud/RE-Toolbox) - Blender addon containing additional utilities to make working with RE Engine files easier. Allows for batch exporting.
  
**Not required but strongly recommended:**
* [RE Chain Editor](https://github.com/NSACloud/RE-Chain-Editor) - Blender addon for creation of chain files. Used to add physics to models.

## Installation
Download the addon from the "Download RE Mesh Editor" link at the top or click Code > Download Zip.

In Blender, go to Edit > Preferences > Addons, then click "Install" in the top right.

Navigate to the downloaded zip file for this addon and click "Install Addon". The addon should then be usable.

To update this addon, navigate to Preferences > Add-ons > RE Mesh Editor and press the "Check for update" button.

## Change Log

### V0.25 - 7/26/2024
* Fixed issue where Blender could give out of bound vertex group indices and cause an error.

### V0.24 - 7/26/2024
* Fixed issue where BaseTwoSideEnable was missing in the UI for MDF flags.

### V0.23 - 7/22/2024
* Fixed mesh triangulation being disabled after previous update.

### V0.22 - 7/21/2024
* Fixed mesh export issue where if vertex weights were below a certain amount, the vertices would snap to the world origin in game.

### V0.21 - 7/12/2024
* Exported meshes are triangulated automatically. This does not alter meshes in the scene, it only affects the exported mesh file.

### V0.20 - 7/11/2024
* Fixed issue where MDFs using render targets (rtex) didn't export correctly.
* Fixed issue with mesh export that caused an error on specific system configurations. 

### V0.19 - 7/6/2024
* Fixed error with "Apply Active MDF" button.

### V0.18 - 7/5/2024
* Added support for Dragon's Dogma 2, Devil May Cry 5, Kunitsu-Gami, Resident Evil 2/3 Non RT, and Resident Evil 7 RT.
* Added support for GPU Buffer data used in DD2 MDF files.
* LOD collections are no longer created upon import if "Import All LODs" is unchecked.
* Fixed issue where the exported local bone matrix was incorrect.

<details>
  <summary>Older Version Change Logs</summary>

### V0.17 - 6/16/2024
* Fixed issue where the preserve bone matrices export option didn't work. 

### V0.16 - 6/14/2024
* Fixed issue where low influence weights would be weighted incorrectly upon export.
* Fixed issue where some single weight meshes wouldn't import with weights

### V0.15 - 6/5/2024
* Fixed issue where exported mesh weights would be incorrect due to rounding issues.

### V0.14 - 5/28/2024
* Fixed issue with importing armatures from mesh files exported with Noesis.

### V0.13 - 5/27/2024
* Bone length of imported armatures is now determined by the area of bone weights. This makes areas with closely grouped bones such as faces look less cluttered. This is purely visual and does not affect export.
* Fixed issue where MDF exporting didn't work correctly for Street Fighter 6.
* Fixed issue where exporting an MDF for SF6 didn't check for material mismatches with the mesh.
* Added MMTRS data importing for MDF files. This is only used with SF6.
* Added more unknown values to the flags section of the MDF material flags.
* Fixed issue where texture files in the addon folder will be backed up when the addon is updated.

### V0.12 - 5/21/2024

* Fixed issue with importing SF6 meshes from the latest update.

### V0.11 - 5/20/2024

* Auto Solve Repeated UVs and Split Sharp Edges no longer modifies the meshes in the scene. The changes will only be applied on the exported mesh.
* Split Sharp Edges export option now requires RE Toolbox.
* Fixed issue where merging armatures didn't work correctly.
* Fixed issue where exporting an MDF with more than one mesh collection in a scene could cause warnings about mismatched materials.
* Fixed issue causing some meshes in RE3 to not be importable.


## V0.10 - 5/4/2024

* Fixed issue where exported tangents were incorrect.
* Fixed issue where an error message didn't show for having no meshes in the exported collection.

### V0.9 - 5/3/2024

* Fixed error that could occur when loose geometry was present when exporting.
* Rotation is now applied on imported objects when Y to Z up is enabled (Rotation is now (0,0,0) instead of (0,90,0). Previously imported meshes will still work correctly on export.
* Textures will no longer be repeatedly try to be loaded if an error occurs during attempting to import them.

### V0.8 - 4/29/2024

* Fixed issue causing UV2 to not export correctly.
* Fixed issue where split normals didn't export correctly.
* Fixed issue where a new collection would not be created when importing a mesh with the same name as an existing mesh.
* Fixed issue where a mesh collection would be assigned in the mesh export options even if it didn't exist.
* Replaced "Add Edge Split Modifier" with "Split Sharp Edges" in the mesh export options. Now disabled by default.
* Added tool tips to the chunk path buttons in the addon preferences.

NOTE: RE Toolbox has also been updated. Be sure to update it as well as it contains important fixes to "Solve Repeated UVs".

### V0.7 - 4/28/2024

* Fixed issue where group IDs would be lost upon export if "Import All LODs" was disabled.

### V0.6 - 4/28/2024

* Beta initial release.

 </details>

## Usage Guide

Video guide coming soon. Images will be added to the text guide once the video is done.

**Quick Model Import Guide**

1. Find the mesh you want to replace inside the extracted .pak files.
2. Create a folder for your mod, then recreate the folder structure leading to the mesh file inside your mod folder starting from the "natives" folder.
3. Import the mesh file from File > Import > RE Mesh. Use the default import settings.
4. Import the model you want to replace it with.
5. Pose your model and rig it to the armature from the imported mesh file.
6. Separate your model by material (Ctrl P > Material) so that every mesh only has one material.
7. Move your meshes into the red .mesh collection either by dragging them onto it in the outliner, or pressing M (Move To Collection).
8. Rename your meshes to the same naming format as the imported mesh. (Example: Group_0_Sub_0__**MaterialName**)
9. Import the .mdf2 file that was alongside the .mesh file.
10. Rename the mdf material objects to your new material names in Object Properties > RE MDF Material Settings > Material Name
11. Change the texture bindings in the RE MDF Material settings to new paths for any textures you want to change.
12. Duplicate or add material presets if necessary. **NOTE: The names and amount of materials in the mdf must match the mesh file or you will get either an invisible model or a checkerboard texture in game.**
13. Open your textures in Photoshop or any image editor with full .dds saving support. (Not Gimp) Install the [Intel DDS Plugin](https://www.intel.com/content/www/us/en/developer/articles/tool/intel-texture-works-plugin.html) if using Photoshop.
14. Adjust the color channels of your textures so that they match the corresponding RE Engine texture's color channel layout.
15. Save edited textures to their own folder as a .dds file. For the compression settings, use BC7 sRGB if it's an albedo/color map or BC7 Linear if it's anything else.
16. In the RE MDF tab on the sidebar, set the Mod Directory to the natives\STM\ folder inside your mod folder.
17. Set the image directory to the directory containing the .dds files you saved.
18. Press "Convert DDS to Tex", then press "Copy Converted Tex Files". The tex files will be placed at whatever path you set them to be in the MDF material.
19. To test the textures, press "Apply Active MDF". Check the console (Window > Toggle System Console) and make sure that there's no warnings about the textures that you created.
20. (Optional) Add bones to the armature to be used as physics bones. Create chains using RE Chain Editor.
21. Export from File > Export > RE Mesh/MDF and put them in the mod folder at their original chunk path.
22. Install the mod folder using Fluffy Manager or use FirstNatives.
## FAQ / Troubleshooting
* **The model has a checkerboard texture or is invisible in game.**

The material names or amount of materials in the mesh and MDF file do not match.
* **The game infinitely loads when the model is loaded.**
  
A texture is not at the path set in the MDF. Or you may be using an outdated .mdf2, .pfb, or .user file in your mod. Make sure that you extracted from the most recent patch pak file.
* **The model is stuck in a T pose**
  
The mesh is not rigged to the armature correctly. Check the the mesh moves along with the armature in pose mode. Also check that the armature is inside the mesh collection.
* **The material looks bugged in game**
  
You may be using an outdated .mdf2 file, be sure to extract from the latest patch pak as materials can change upon updates.

## Credits
[Monster Hunter Modding Discord](https://discord.gg/gJwMdhK)

[Modding Haven Discord](https://discord.gg/modding-haven-718224210270617702)
- [AsteriskAmpersand](https://github.com/AsteriskAmpersand) - Mesh format research and tex conversion code
- [AlphaZomega](https://github.com/alphazolam/) - RE Mesh 010 Template and Noesis plugin
- [CG Cookie](https://github.com/CGCookie) - Addon updater module
- [matyalatte](https://github.com/matyalatte/Texconv-Custom-DLL) - DirectX Texconv DLL library
