<p align="center"> <img width="138" alt="ARKit-Logo" src="https://user-images.githubusercontent.com/61129822/131022584-30e4e543-29ee-410a-a3cc-1287eed89cd1.png"><img width="171" alt="RealityKit-Logo" src="https://user-images.githubusercontent.com/61129822/131022417-f952a41c-22ed-45ce-96bd-e4365b8bd781.png">
</p>
 
# Introduction to Augmented Reality on iOS
  
This page is intended to be an introduction to Augmented Reality on iOS - including frameworks, best practices, resources, and more.  Apple has created a wonderful augmented reality platform - but with technology and frameworks evolving so quickly, things can get a bit confusing.  ARKit, RealityKit, SceneKit, and Metal, are often brought up when discussing an augmented reality application.  Often times discussed in tandem with one another, or sometimes individually, this document will help provide clarity.


# Table of Contents

- [Comparision: ARKit + SceneKit vs RealityKit](https://github.com/hunterh37/Introduction-to-Augmented-Reality-on-iOS#comparision-arkit-scenekit-realitykit---whats-the-difference)
- [ARKit](https://github.com/hunterh37/Introduction-to-Augmented-Reality-on-iOS#arkit)
- [RealityKit](https://github.com/hunterh37/Introduction-to-Augmented-Reality-on-iOS#realitykit)
- [Common Components in an Augmented Reality Application](https://github.com/hunterh37/Introduction-to-Augmented-Reality-on-iOS#common-components-in-an-augmented-reality-application)
- [Media](https://github.com/hunterh37/Introduction-to-Augmented-Reality-on-iOS#media)
- [Resources](https://github.com/hunterh37/Introduction-to-Augmented-Reality-on-iOS#resources)
- [Apple Example Projects](https://github.com/hunterh37/Introduction-to-Augmented-Reality-on-iOS#resources)
- [Conclusion / Future of AR Apps on iOS](https://github.com/hunterh37/Introduction-to-Augmented-Reality-on-iOS#conclusion--future-of-ar-apps-on-ios)


# Comparision: ARKit, SceneKit, RealityKit - What's the difference?

Apple’s ARKit platform was originally built on top of SceneKit — a 3D graphics framework developed for mobile games. This gave a solid foundation to  leverage SceneKit’s rendering technology to create an early platform for augmented reality applications. **RealityKit** was introduced after **ARKit and SceneKit,** as a way to simplify the workflow of creating an augmented reality application. RealityKit offers many features out of the box, such as: handling gestures, collisions, and applying real world lighting effects to objects.

**ARKit** (iOS 11)

**ARKit** captures devices data that is used to render objects in a realistic method - it combines device motion tracking, camera scene capture, and advanced scene processing.  SceneKit offers a way to render AR content using the data provided from ARKit.

**SceneKit** (iOS 8)

**SceneKit** was originally developed for mobile games. In an augmented reality application, SceneKit uses the data from ARKit to render objects in a realistic method.  SceneKit provides a way to drill down and manage these objects, but many of the features were not created for an augmented reality application.  This is where RealityKit comes in.


**RealityKit** (iOS 13)

**RealityKit** was created as a way to simplify the creation of building augmented reality applications. Out of the box, RealityKit provides many of the features that would traditionally require manual calculations and rendering. 

<img src="https://user-images.githubusercontent.com/61129822/130316117-3461a071-e8db-4e43-90b9-191a7b2a278d.png" data-canonical-src="https://user-images.githubusercontent.com/61129822/130316117-3461a071-e8db-4e43-90b9-191a7b2a278d.png" width="500" height="250" />

_RealityKit mapping of virtual object on table_



-----
<img width="138" alt="ARKit-Logo" src="https://user-images.githubusercontent.com/61129822/131022584-30e4e543-29ee-410a-a3cc-1287eed89cd1.png">


# ARKit 

ARKit is an augmented reality framework for iOS, available on both iPhone and iPad. ARKit lets developers place digital objects in the real world by blending the camera on the screen with virtual objects, allowing users to interact with these objects in a real space.

It does this by using the camera on iOS devices to create a map of the area, detecting things like tabletops, floors and the location of the device in the physical space using CoreMotion data. No calibration is required from the user.

ARKit can run on most modern iPhones and iPads, utilizing SceneKit integration to render the objects. ARKit also makes it possible to integrate with third-party tools such as Unity and Unreal Engine, to use their rendering capabilities.

ARKit Features
- [Face Tracking](https://developer.apple.com/documentation/arkit/content_anchors/tracking_and_visualizing_faces)
- Front + Back Camera data collection
- [People / Object Occlusion](https://developer.apple.com/documentation/arkit/camera_lighting_and_effects/occluding_virtual_content_with_people)
- Lighting & Shadows estimation
- Motion Capture (body tracking)
- Scene Understanding (Surface detection)
- [World Tracking](https://developer.apple.com/documentation/arkit/arworldtrackingconfiguration)
- [ARWorldMaps](https://developer.apple.com/documentation/arkit/arworldmap) (Save and relaunch a scene as a world map)
- [Location Anchors](https://developer.apple.com/documentation/arkit/content_anchors/tracking_geographic_locations_in_ar)
- Multiplayer Connectivity

<p>
<img width="141" alt="RealityKit-Logo" src="https://user-images.githubusercontent.com/61129822/131062968-7b24dba8-b146-454a-8f47-fd8aaaae57a5.png">
 -
<img width="371" alt="RealityKit-Logo" src="https://user-images.githubusercontent.com/61129822/131062986-fd0ecc65-ed25-423d-988c-0df3f45b7a7e.jpg">
</p>


-----

<img width="171" alt="RealityKit-Logo" src="https://user-images.githubusercontent.com/61129822/131022417-f952a41c-22ed-45ce-96bd-e4365b8bd781.png">

# RealityKit 

The RealityKit framework was built from the ground up specifically for augmented reality with photo-realistic rendering, camera effects, animations, physics, and more. With native Swift APIs, ARKit integration, incredibly realistic physics-based rendering, transform and skeletal animations, spatial audio, and rigid body physics, RealityKit makes AR development faster and easier than ever before.


RealityKit Features

- Leverages data from ARKit for realistic rendering of augmented reality experiences 
- Gesture handling (tap to move objects)
- Animations (start or stop multiple animations on different objects)
- Shaders (allows for complex rendering of objects)
- Physics (Object movement and collision)
- Lighting & Shadows estimation

Materials

- SimpleMaterial
- UnlitMaterial
- OcclusionMaterial
- VideoMaterial
- PhysicallyBasedMaterial
- CustomMaterial


_____ 

# Quick Start - ARKit + SceneKit Implementation

- coming soon
 
-----


# Quick Start - RealityKit Implementation

Quickly add a .usdz file to an ```ARView```  using ```Entity.load  ```
```swift
  import RealityKit
            
  //Initialize an ARView programically
  let arView = ARView(frame: CGRect(x: 0, y: 0, width: 0, height: 0))
  
  //Or connect via IBOutlet
  @IBOutlet weak var arView: ARView!
  
  //Add a .usdz object to the ARView
  let anchor = AnchorEntity()
  let modelEntity = try! Entity.loadModel(named: "name_of_usdz_file")  
  anchor.addChild(modelEntity)
  arView.scene.addAnchor(anchor)
            

```


_Note:  Make sure to enable the **Privacy - Camera Usage Description** setting in info.plist_


# Common Components in an Augmented Reality Application


<img width="400" alt="ARKit-Logo" src="https://user-images.githubusercontent.com/61129822/131063043-18e1c9d8-bf40-4fd4-bc95-399d149acc07.png">


- [ARView](https://developer.apple.com/documentation/realitykit/arview)
    - _A view that displays an augmented reality experience that incorporates content from RealityKit._
    - This is what allows us to see 3d models placed into the environment, using the camera view. 

- [Scene](https://developer.apple.com/documentation/realitykit/scene)
    - A container that holds the collection of entities rendered by an AR view.
    - You don’t create a Scene instance directly. Instead, you get the one and only scene associated with a view from the scene property of an ARView instance.
    - To add content to the view’s scene, you first create and add one or more AnchorEntity instances to the scene’s anchors collection.

- [AnchorEntity](https://developer.apple.com/documentation/realitykit/anchorentity) 
    - Anchors tell RealityKit how to pin virtual content to real world objects, like flat surfaces or images. You then add a hierarchy of other Entity instances to each anchor to indicate the geometry and behaviors that RealityKit should render at a given anchor point.

- [Entity](https://developer.apple.com/documentation/realitykit/entity)
    - An element of a RealityKit scene to which you attach components that provide appearance and behavior characteristics for the entity.
    - You create and configure entities to embody objects that you want to place in the real world in an AR app. You do this by adding Entity instances to the Scene instance associated with an ARView.

----------------

# Useful Snippets

```swift

// create an entity from local .usdz file
 private func addEntity() {
        let anchor = AnchorEntity()
        let modelEntity = try! Entity.loadModel(named: "Local_Filename_Here")
        
        anchor.addChild(modelEntity)
        arView.scene.addAnchor(anchor)
 }

//create a cube entity with texture from remote image url

private func createCubeWithRemoteTexture(remoteUrl: URL) {
        // First create a local temporary file URL to store the image at the remote URL.
        let fileURL = FileManager.default.temporaryDirectory.appendingPathComponent(UUID().uuidString)
        // Download contents of imageURL as Data.  Use a URLSession if you want to do this asynchronously.
        let data = try! Data(contentsOf: remoteURL)
        
        // Write the image Data to the file URL.
        try! data.write(to: fileURL)
        do {
            // Create a TextureResource by loading the contents of the file URL.
            let texture = try TextureResource.load(contentsOf: fileURL)
            var material = SimpleMaterial()
            material.baseColor = MaterialColorParameter.texture(texture)
         
            let entity = ModelEntity(mesh: .generateBox(size: 0.5), materials: [material])
            let anchor = AnchorEntity(.plane(.any, classification: .any, minimumBounds: .zero))
            
            entity.generateCollisionShapes(recursive: true)
            arView.installGestures(for: entity)
            
            anchor.addChild(entity)
            arView.scene.addAnchor(anchor)
        } catch {
            print(error.localizedDescription)
        }
    }



//save an AR world map to url

func writeWorldMap(_ worldMap: ARWorldMap, to url: URL) throws {
    let data = try NSKeyedArchiver.archivedData(withRootObject: worldMap, requiringSecureCoding: true)
    try data.write(to: url)
}

//load an AR worldmap from url

func loadWorldMap(from url: URL) throws -> ARWorldMap {
    let mapData = try Data(contentsOf: url)
    guard let worldMap = try NSKeyedUnarchiver.unarchivedObject(ofClass: ARWorldMap.self, from: mapData)
        else { throw ARError(.invalidWorldMap) }
    return worldMap
}

```

-----------------

# Media: 
<img src="https://user-images.githubusercontent.com/61129822/130653683-7d117d64-90b3-4cd9-88f3-6ef8df582a72.jpg" data-canonical-src="https://user-images.githubusercontent.com/61129822/130653683-7d117d64-90b3-4cd9-88f3-6ef8df582a72.jpg" width="250" height="500" />

_Apple Measure App_

<img src="https://user-images.githubusercontent.com/61129822/130653684-2f01d875-8ecd-47e0-92cd-42f0daec07bf.png" data-canonical-src="https://user-images.githubusercontent.com/61129822/130653684-2f01d875-8ecd-47e0-92cd-42f0daec07bf.png" width="250" height="500" />

_Lowes Envision App_

<img src="https://user-images.githubusercontent.com/61129822/130724025-900e514e-a21e-4aac-b2d9-f98cb076b681.png" data-canonical-src="https://user-images.githubusercontent.com/61129822/130724025-900e514e-a21e-4aac-b2d9-f98cb076b681.png" width="250" height="250" />

_Face Tracking_

Veep - Augmented Reality Social Network: https://youtu.be/HDHnbd8QHGU


# Resources:  

**Apple Tools**

<img width="400" alt="RealityKit-Logo" src="https://user-images.githubusercontent.com/61129822/131024113-e19d1009-3a9c-4b5b-8d28-889465b00b3a.jpg">

https://developer.apple.com/augmented-reality/tools/

- Reality Composer - found within Xcode developer menu 

- Reality Converter - Download from Apple website, allows for quick conversion of common 3d media formats into .usdz or .reality for ARKit compatibility. Common filetypes include: .fbx and .obj

- Object Capture - https://developer.apple.com/augmented-reality/object-capture/
      - Turn photos from your iPhone or iPad into high‑quality 3D models that are optimized for AR using the new Object Capture API on macOS Monterey. Object Capture uses photogrammetry to turn a series of pictures taken on your iPhone or iPad into USDZ files that can be viewed in AR

**Useful Links (Apple.com)**

- Apple Quick Look Gallery (AR previews on Safari): https://developer.apple.com/augmented-reality/quick-look/
- Apple Developer Augmented Reality Homepage - https://developer.apple.com/augmented-reality/

**Apple Example Projects:**

- WWDC 2021 Fish Scene: https://developer.apple.com/documentation/realitykit/building_an_immersive_experience_with_realitykit
- WWDC 2021 Reality Kit 2 Example Project: https://developer.apple.com/documentation/realitykit/building_an_immersive_experience_with_realitykit
- Saving and Loading World Data: https://developer.apple.com/documentation/arkit/data_management/saving_and_loading_world_data#see-also
- Tracking and Visualizing Planes: https://developer.apple.com/documentation/arkit/content_anchors/tracking_and_visualizing_planes
- Tracking and Visualizing Faces: https://developer.apple.com/documentation/arkit/content_anchors/tracking_and_visualizing_faces

**Other Example Projects:**

- [ARKit Sampler](https://github.com/shu223/ARKit-Sampler) - a sample implementation of many ARKit features.



**3D Model Marketplaces**

- https://sketchfab.com/
- https://www.turbosquid.com
- https://assetstore.unity.com
- https://free3d.com/

**Augmented Reality iOS Timeline**

- 2012 Vuforia Engine (3rd party AR framework)
- 2017 ARKit Introduction
- 2018 ARKit 2
- 2019 ARKit 3
- 2019 RealityKit
- 2020 ARKit 4
- 2021 RealityKit 2
- 2021 ARKit 5


Sources: 
- TechRepublic ARKit Cheat Sheet: https://www.techrepublic.com/article/apples-arkit-everything-the-pros-need-to-know/
- Lowes AR App: https://www.marketingdive.com/news/lowes-debuts-2-ar-apps-to-help-people-furnish-their-homes/505798/
- Shaders: https://maxxfrazer.medium.com/getting-started-with-realitykit-shaders-468c55738f8e
- ARKit Sample Project: https://github.com/shu223/ARKit-Sampler


# Conclusion / Future of AR Apps on iOS

- RealityKit + SwiftUI + Apple Silicon = Apple Glasses

With such a strong augmented reality platform, it certainly seems Apple is preparing for their launch of Apple Glasses.  These tools and frameworks have been quietly brewing in the background - the major bugs, flaws, and quirks, have all been worked out. Apple Glasses might spark a consumer revolution similar to the first iPhone, so developers and anyone involved in mobile app development should pay attention to this space.




