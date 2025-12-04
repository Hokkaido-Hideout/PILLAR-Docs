# HKH Pillars Generator Plugin Documentation

The **HKH Pillars Generator** is a professional procedural pillar generation plugin for Unreal Engine 5. This powerful editor tool enables artists and designers to create customizable architectural pillars with real-time preview, material baking, and export capabilities.

![Pillar Generator Interface](https://www.dropbox.com/scl/fi/7n6f7q4tuvvy3pedkcicd/45a9cfcc-bda9-4b3f-b5fb-7802c3d57123.jpg?rlkey=8zrscestq6t2ultjpv4n9ir7f&st=62gy1vad&raw=1)

## Features

### 🎯 Core Generation
- **Procedural Pillar Creation**: Generate pillars with customizable parameters in real-time
- **Multiple Architectural Styles**: Support for Doric, Ionic, Corinthian, Tuscan, Romanesque, Gothic, Baroque, Modern, and Cyberpunk styles
- **Real-time 3D Preview**: Interactive viewport with immediate visual feedback
- **Non-destructive Workflow**: Preserve original parameters while iterating

### 🏗️ Structural Controls
- **Generator Settings**: Ring count, surface map resolution, and domain controls
- **Damage & Weathering**: Age, moss accumulation, crack intensity, and surface erosion
- **Visual Styles**: Blockie, Stylised, and Realistic rendering domains
- **Material System**: Automatic material assignment based on architectural style

### 🎨 Material & Texturing
- **Surface Baking**: Automated curvature, AO, and normal map generation
- **Texture Graph Processing**: Smart material assignment using texture graphs
- **Material Instancing**: Dynamic material creation with parameter control
- **Export-ready Materials**: Fully configured materials for game-ready assets

### ⚙️ Technical Features
- **Dynamic Mesh Components**: Real-time mesh updates and regeneration
- **Collision Generation**: Automatic UCX physics mesh creation
- **Asset Export**: Export to static mesh with proper LODs
- **Preset System**: Save and load pillar configurations

## Installation

### Requirements
- Unreal Engine 5.0 or newer
- Windows 10/11 (64-bit)
- 8GB RAM minimum, 16GB recommended
- DirectX 11/12 compatible GPU

### Installation Steps

1. **Download the Plugin**
   - Obtain the plugin from the [FAB Marketplace](https://thehokkaidohideout.com) or internal distribution

2. **Plugin Installation**
   - Navigate to your project's `Plugins` folder
   - Create `HKHPillarGEN` directory if it doesn't exist
   - Extract plugin files to `YourProject/Plugins/HKHPillarGEN/`

3. **Enable the Plugin**
   - Open your Unreal Engine project
   - Go to `Edit → Plugins`
   - Search for "HKH Pillars Generator"
   - Check the "Enabled" checkbox
   - Restart the editor when prompted

4. **Verify Installation**
   - After restart, check the main menu for "HKH Tools" menu entry
   - The Pillar Builder tab should be available in the editor

## Getting Started

### Accessing the Tool

**Method 1: Content Browser**
- Right-click in Content Browser → `HKH → Pillar Generator`

**Method 2: Editor Menu**
- Go to `File → Pillar Generator`

**Method 3: Toolbar**
- Click the "HKH Tools" button in the main toolbar

### Creating Your First Pillar

1. **Open the Pillar Builder**
   - The interface opens with a default pillar in the viewport

2. **Generate Initial Model**
   - Click **"Generate Model"** to create your first pillar
   - The viewport will display the generated mesh

3. **Apply a Preset**
   - Browse the **Presets** panel on the left
   - Click any preset (e.g., "Stylised Corinthian") to apply
   - Regenerate the model to see changes

4. **Customize Parameters**
   - Use the **Generator** panel on the right to adjust:
     - Ring Count
     - Surface Map Size
     - Visual Style
     - Architecture Type

## Interface Overview

### Main Toolbar
| Button | Function | Description |
|--------|----------|-------------|
| **Generate Model** | `GenerateDynaMesh()` | Creates/updates the pillar mesh |
| **Bake Surface** | `BakeSurfaceMaps()` | Generates surface textures (AO, Normal, Curvature) |
| **Export Mesh** | `ExportDynaMesh()` | Exports to Static Mesh asset |
| **Export Physics** | `ExportMeshLOD()` | Generates collision mesh |
| **Help** | `GetHelp()` | Opens documentation |

### Panels

#### Presets Panel (Left)
- **Style Presets**: Pre-configured architectural styles
- **Custom Presets**: User-saved configurations
- **Thumbnail Previews**: Visual representation of each preset

#### Viewport (Center)
- **3D Preview**: Real-time pillar visualization
- **Navigation**: Standard UE5 viewport controls
- **Visual Feedback**: Live updates during parameter changes

#### Generator Panel (Right)
- **Pillar Settings**: Core generation parameters
- **Damage Settings**: Weathering and age effects
- **Material Controls**: Surface properties and textures

## Parameters Reference

### Generator Settings
| Parameter | Type | Range | Description |
|-----------|------|-------|-------------|
| **Ring Count** | Integer | 3-64 | Number of vertical segments |
| **Surface Map Size** | Enum | 512-2048 | Texture resolution for baking |
| **Visual Style** | Enum | Blockie, Stylised, Realistic | Rendering quality level |
| **Architecture** | Enum | Doric, Ionic, Corinthian, etc. | Architectural style |

### Damage Settings
| Parameter | Type | Range | Description |
|-----------|------|-------|-------------|
| **Age** | Float | 1-100 | Overall weathering amount |
| **Moss Amount** | Float | 0-100 | Moss accumulation level |
| **Crack Intensity** | Float | 0-1 | Surface cracking severity |
| **Surface Erosion** | Float | 0-1 | Material wear and tear |

### Material Assignment
The plugin automatically assigns materials based on architectural style:

| Architecture | Material Type | Characteristics |
|--------------|---------------|-----------------|
| **Doric/Tuscan** | Concrete | Heavy, weathered stone appearance |
| **Ionic/Corinthian** | Marble | Polished, refined classical look |
| **Baroque** | Wood | Gilded or painted wood finishes |
| **Gothic** | Concrete | Dark stone, iron-reinforced |
| **Modern** | Concrete | Brutalist, raw concrete |
| **Cyberpunk** | Steel | Future alloy, brushed metal |

## Workflow Guide

### Basic Pillar Creation
1. **Start with Preset**: Choose a base style from presets
2. **Generate Model**: Create the initial mesh
3. **Adjust Parameters**: Fine-tune in Generator panel
4. **Bake Surfaces**: Generate textures for materials
5. **Export**: Save as Static Mesh for use in levels

### Advanced Material Workflow
1. **Generate Model** with desired geometry
2. **Click Bake Surface** to create:
   - Curvature Map (CV)
   - Ambient Occlusion (AO)
   - Normal Map (NM)
3. **Texture Graph Processing** automatically:
   - Applies appropriate material graph
   - Creates Material Instances
   - Assigns baked textures
   - Adjusts parameters based on damage settings

### Export Options
- **Export Mesh**: Creates Static Mesh asset in `/Game/HKH/` folder
- **Export Physics**: Generates simplified collision mesh
- **Materials**: Exports with fully configured material instances

## Tutorials

### Quick Start: Classical Column
1. Open Pillar Builder from Content Browser
2. Click "Stylised Corinthian" preset
3. Click **Generate Model**
4. Adjust Ring Count to 24 for smoother curves
5. Click **Bake Surface** to generate textures
6. Click **Export Mesh** to save as asset

### Creating Custom Style
1. Start with "Stylised Modern" preset
2. In Generator panel:
   - Set Architecture: `Corinthian`
   - Set Visual Style: `Realistic`
   - Adjust Damage → Age: `75`
   - Set Moss Amount: `30`
3. Generate Model and Bake Surface
4. Save as new preset for future use

### Performance Optimization
- Use `Blockie` visual style for distant LODs
- Lower Surface Map Size for non-hero assets
- Reduce Ring Count for optimized geometry

## Troubleshooting

### Common Issues

**Plugin Not Appearing**
- Verify plugin is enabled in Edit → Plugins
- Check project supports C++ plugins
- Restart editor after enabling

**Generate Model Fails**
- Ensure viewport is properly initialized
- Check for console errors in Output Log
- Verify DynamicMeshComponent is available

**Bake Surface Errors**
- Confirm pillar mesh is generated first
- Check disk space for texture creation
- Verify material graphs are properly configured

**Export Problems**
- Ensure target directory (`/Game/HKH/`) exists
- Check write permissions for project folder
- Verify mesh has valid geometry

### Performance Tips
- Use lower Surface Map Size (512) for multiple pillars
- Generate collision meshes only when needed
- Bake surfaces after finalizing geometry
- Use presets to quickly iterate on styles

## Technical Details

### Supported Platforms
- Windows 64-bit
- Built for Unreal Engine 5.5+
- DirectX 11/12

### File Structure
```
Plugins/
└── HKHPillarGEN/
    ├── Content/
    │   ├── PillarPresets.json
    │   └── MaterialGraphs/
    ├── Source/
    │   └── HKHPillarGEN/
    └── Resources/
```

### API Reference
The plugin exposes several key functions for integration:

```cpp
// Core generation
GenerateDynaMesh()
BakeSurfaceMaps()
ExportDynaMesh()

// Utility functions
GetPreviewComponent()
PlacePreviewOnGround()
CaptureViewportThumbnail()
```

## Support

### Documentation
- 📖 [Full Documentation](https://pll.hkh-interactive.com)
- 💬 [Discord Community](https://discord.gg/BzTRUqPEAF)
- 🐛 [Bug Reports](mailto:hokkaido.hideout@gmail.com)

### Technical Support
For technical issues, please include:
1. Unreal Engine version
2. Plugin version
3. Error log from Output Log
4. Steps to reproduce the issue
5. System specifications

---

## Changelog

### Version 1.0.0
- Initial release
- 9 architectural styles
- Real-time preview
- Surface baking system
- Preset management
- Export functionality