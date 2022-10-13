# Sun Temple URP Conversion  

There is a great asset on the unity asset store called 'Sun Temple' by Sandro T. It has surface shaders which only work with built-in pipeline and I wanted to convert them to URP.  

[https://assetstore.unity.com/packages/3d/environments/sun-temple-115417](https://assetstore.unity.com/packages/3d/environments/sun-temple-115417)

In this package, the surface shaders have been converted to shadergraph and the materials using autodesk shader have been replaced with Lit shader. The package contains a few textures that put the roughness channel into the alpha channel of the albedo texture for smoothness.  

The demo scene is changed only to remove the directional light cookie which looks wrong in URP, as well as hiding some collider objects.  

You are intended to create an empty URP project, import 'Sun Temple' from the asset store (uncheck the box for the post processing folder - it's incompatible with URP and a specific file causes an error which prevents you from going into play mode). Next import the package in this repo and then open the demo scene. You should see everything rendering right at this point because all incompatible materials were replaced.  

One obvious issue you will notice is the terrain grass looks wrong and the wind makes it move around in a way that doesn't look good (clipping through walls etc). The reason for this is because in built-in pipeline, the terrain grass shader is overridden by a custom one. You can't do that easily in URP, so I just left it alone. 
