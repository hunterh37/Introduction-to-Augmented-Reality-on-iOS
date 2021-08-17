# Introduction to Augmented Reality on iOS

This page is intended to be an introduction to Augmented Reality on iOS - including frameworks, best practices, resources, and more.  Apple has created a wonderful augmented reality platform - but with technology and frameworks evolving so quickly, things can get a bit confusing.  ARKit, RealityKit, SceneKit, and Metal, are often brought up when discussing an augmented reality application.  Often times discussed in tandem with one another, or sometimes individually, this document will help provide clarity.

# Table of Contents

- ARKit
- RealityKit
- SceneKit

# Quick Start (RealityKit)

```swift
  import RealityKit
            
  //create arview
  let arView = ARView(frame: CGRect(x: 0, y: 0, width: 0, height: 0))
            

```



# Common Components in an Augmented Reality Application

- ARSCNView - https://developer.apple.com/documentation/arkit/arscnview
    - A view that blends virtual 3d content from SceneKit into your augmented reality experience.

- Scene -  https://developer.apple.com/documentation/arkit/arscnview/2875547-scene
    - The SceneKit scene to be displayed in the view.
        - Can be a single 3d model, or a collection of models bundled together into a scene.

- SCNNode - https://developer.apple.com/documentation/scenekit/scnnode
    - A structural element of a scene graph, representing a position and transform in a 3D coordinate space, to which you can attach geometry, lights, cameras, or other displayable content.
        - File types: .usdz + .reality 


# Augmented Reality iOS Timeline

- 2012 Vuforia Engine
- 2017 ARKit Introduction
- 2018 ARKit 2
- 2019 ARKit 3
- 2019 RealityKit
- 2020 ARKit 4
- 2021 RealityKit 2
- 2021 ARKit 5



# Resources:  

**Apple Tools**
- Reality Composer - found within Xcode developer menu
- Reality Converter - Download from Apple website, allows for quick conversion of common 3d media formats into .usdz or .reality for ARKit compatibility. Common filetypes include: .fbx and .obj

**Useful Links (Apple.com)**

- Apple Quick Look Gallery (AR previews on Safari): https://developer.apple.com/augmented-reality/quick-look/
- Apple Developer Augmented Reality Homepage - https://developer.apple.com/augmented-reality/

**Apple Example Projects:**

- 2021 WWDC Fish Scene: https://developer.apple.com/documentation/realitykit/building_an_immersive_experience_with_realitykit
- Saving and Loading World Data: https://developer.apple.com/documentation/arkit/data_management/saving_and_loading_world_data#see-also
- Tracking and Visualizing Planes: https://developer.apple.com/documentation/arkit/content_anchors/tracking_and_visualizing_planes


**WWDC Videos**:
- ARKit 4 2020: https://www.youtube.com/watch?v=SpZyxHkmfqE



**3D Model Marketplaces**

- https://sketchfab.com/
- https://www.turbosquid.com
- https://assetstore.unity.com
- https://free3d.com/
