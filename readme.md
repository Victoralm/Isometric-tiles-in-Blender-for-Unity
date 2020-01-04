# Isometric tiles on Blender for Unity

This is my attempting to standardize the procedure of creating isometric tilesets on Blender (2.8x).

The basic [.blend](resources/BaseIsometricTilesets.blend) file (made with blender 2.81) and the reference images ([512px](resources/CubeTileBase_512.png), [768px](resources/CubeTileBase_768.png), [1024px](resources/CubeTileBase_1024.png)) can be found at the resources folder.

______________
![#f03c15](https://placehold.it/15/f03c15/000000?text=+) **`Attention:`**

`The result rendered images of the cubes will always have 1024px. So, the desired ones with 512px and 768px, will need to be manually cut on an image editor to proper work on Unity.`
______________

## **Blender setup**

### **Eevee**

| **Description**                                                                                                                                               |                                    **Image reference** |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------- | -----------------------------------------------------: |
| On the render properties tab, on Film dropdown, enable Transparent option. Also, on Color Management dropdown, set Medium Contrast at Look option as follows: | ![CamForCubes_512BgImg](resources/imgs/EeveeSetup.png) |

### Cameras

#### **Change between cameras**

| **Description**                                                                                                                                                                |                                        **Image reference** |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------: |
| Use the "CamForPlanes" camera to render planes, and the "CamForCubes" to render cube like tiles. Is possible to change between cameras on the Scene Properties tab as follows: | ![CamForCubes_512BgImg](resources/imgs/CameraChanging.png) |

#### **Camera for Planes**

| **Location**    |                                                           **Rotation** |
| --------------- | ---------------------------------------------------------------------: |
| X: 10           |                                                                 X: 60º |
| Y: -10          |                                                                  Y: 0º |
| Z: 8.17         |                                                                 Z: 45º |
| Image reference | ![CamForPlanes_Transforms](resources/imgs/CamForPlanes_Transforms.png) |

**Lens**

| **Property**       |                                                  **Value** |
| ------------------ | ---------------------------------------------------------: |
| Type               |                                               Orthographic |
| Orthographic Scale |                                                      2.800 |
| Image reference    | ![CamForPlanes_Lens](resources/imgs/CamForPlanes_Lens.png) |

**Render Size**

| **Description**                                                                                                                |                                                 **Image reference** |
| ------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------: |
| For rendering with the "CamForPlanes" camera, the output resolution need to be **_X: 512 px_** and **_Y: 256 px_** as follows: | ![CamForCubes_512BgImg](resources/imgs/CamForPlanes_RenderSize.png) |

#### **Camera for Cubes**

| **Location**    |                                                         **Rotation** |
| --------------- | -------------------------------------------------------------------: |
| X: 10           |                                                               X: 60º |
| Y: -10          |                                                                Y: 0º |
| Z: 9.6          |                                                               Z: 45º |
| Image reference | ![CamForCubes_Transforms](resources/imgs/CamForCubes_Transforms.png) |

**Lens**

| **Property**       |                                                    **Value** |
| ------------------ | -----------------------------------------------------------: |
| Type               |                                                 Orthographic |
| Orthographic Scale |                                                        5.600 |
| Image reference    | ![CamForCubes_512BgImg](resources/imgs/CamForCubes_Lens.png) |

**Render Size**

| **Description**                                                                                                                |                                                **Image reference** |
| ------------------------------------------------------------------------------------------------------------------------------ | -----------------------------------------------------------------: |
| For rendering with the "CamForCubes" camera, the output resolution need to be **_X: 512 px_** and **_Y: 1024 px_** as follows: | ![CamForCubes_512BgImg](resources/imgs/CamForCubes_RenderSize.png) |

______________
![#86ca58](https://placehold.it/15/86ca58/000000?text=+) **`Attention:`**

`I did use background images on the "CamForCubes" camera to set the correct size of each cube.`
______________

### Cubes

#### **Standard Cube for Tile 512px**

**Scale:**

| **Axis** | **Value** |
| -------- | --------: |
| X        |      1.98 |
| Y        |      1.98 |
| Z        |      1.61 |

| **Description**                                                                                                                |                                              **Image reference** |
| ------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------: |
| Used "CubeTileBase_512.png" as background image of the "CamForCubes" camera, with _**Offset Y**_ of _**-0.25000**_ as follows: | ![CamForCubes_512BgImg](resources/imgs/CamForCubes_512BgImg.png) |

#### **Standard Cube for Tile 768px**

**Scale:**

| **Axis** | **Value** |
| -------- | --------: |
| X        |      1.98 |
| Y        |      1.98 |
| Z        |      3.23 |

| **Description**                                                                                                                |                                              **Image reference** |
| ------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------: |
| Used "CubeTileBase_768.png" as background image of the "CamForCubes" camera, with _**Offset Y**_ of _**-0.12500**_ as follows: | ![CamForCubes_768BgImg](resources/imgs/CamForCubes_768BgImg.png) |

#### **Standard Cube for Tile 1024px**

**Scale:**

| **Axis** | **Value** |
| -------- | --------: |
| X        |      1.98 |
| Y        |      1.98 |
| Z        |      4.84 |

| **Description**                                                                                                                |                                                **Image reference** |
| ------------------------------------------------------------------------------------------------------------------------------ | -----------------------------------------------------------------: |
| Used "CubeTileBase_1024.png" as background image of the "CamForCubes" camera, with _**Offset Y**_ of _**0.00000**_ as follows: | ![CamForCubes_1024BgImg](resources/imgs/CamForCubes_1024BgImg.png) |

## **Unity setup**

After had some tiles, is time to create a new 2D Unity project and bring yours tiles inside it.
The setup of the tilemap is very simple.

| **Description**                                                                                                                                                                                          |                                                         **Image reference** |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------: |
| On the Hierarchy panel, right click and pick Tilemap as follows:                                                                                                                                         |            ![CamForCubes_1024BgImg](resources/imgs/Unity_CreateTileset.png) |
| Select the Grid GameObject on the Hierarchy panel. And, on the Inspector panel -> Grid component tab, set the Cell Size X: 5.1 and Y: 2.55. Also, set Cell Layout to Isometric as follows:               |            ![CamForCubes_1024BgImg](resources/imgs/Unity_GridComponent.png) |
| Optional: Select the Tilemap GameObject (the child of the Grid GameObject) on the Hierarchy panel. And, on the Inspector panel -> Tilemap Renderer component tab, set the Mode to Individual as follows: | ![CamForCubes_1024BgImg](resources/imgs/Unity_TilemapRendererComponent.png) |
| Optional: On the menu Edit -> Project Settings, go to the Graphics options an set the Transparency Sort Axis to X: 0, Y: 1 and Z: 0, as follows:                                                         |  ![CamForCubes_1024BgImg](resources/imgs/Unity_ProjectSettingsGraphics.png) |
| Open the Tile Palette panel via menu Window -> 2D -> Tile Palette. Then, on the Tile Palette panel, create a new palette giving it a name, set Grid to Isometric and Cell Size to Automatic, as follows: |              ![CamForCubes_1024BgImg](resources/imgs/Unity_TilePalette.png) |
| Drag and drop yours sprites (the tiles made on Blender) inside the Tile Palette panel grid.                                                                                                              |                                                                             |
| Start creating your map.                                                                                                                                                                                 |                                                                             |

**Have fun!!**
