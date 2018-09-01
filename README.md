# DissolveParticleShader
Dissolved particles shaders.

Author: Alberto Mellado Cruz
Date: 01/09/2018

This is a shader that enables dissolving particles with the alpha from the particle system editor. 
It also uses the Unity's custom particle data to add an offset to it.


![Alt Text](https://github.com/albertomelladoc/DissolveParticleShader/blob/master/Tutorial.gif)


1. Set Up: 
Create a particle system that emits sphere meshes and a Unlit Shader

2. Particle Texture: 
Add a particle texture if you want.

3. Rendering: 
Add a Soft Additive blend, disable the Zwrite and Cull the back.

4. Get Particle Color: 
Add to appdata and v2f "float4 color: COLOR"; 
In vetex: o.color = v.color;
In fragment: "col*= i.color;" or "col.rgb*= i.color.rgb" (One is also with alpha the other without)

5. Noise
Add a noise texture and use discard when the color.a <= noise.r

6. Offset (Optional)
Using particles custom data pass a random value to the noise uvs.


