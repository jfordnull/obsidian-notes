Shader language depends on target environment. The two I've seen most regularly are:
- GLSL (OpenGL Shading Language)
- HLSL (High Level Shader Language, Direct3D's graphics language)
# Vertex Shader

Vertex shaders position the vertices of our geometry. We'll pass matrices describing vertex positions, mesh transformations, camera information to the shader. The GPU follows the shader's instructions to project each "3D" vertex onto our 2D render space, or canvas. (GPU applies the shader to thousands of vertices in parallel.)

Two types of data:
- **Attributes**, e.g. individual vertex position, which differ per vertex
- **Uniforms**, e.g. camera transform, a mesh transform, etc., consistent across vertices
# Fragment Shader

Used to color each visible fragment of the geometry. We don't use attributes in the fragment shader. We can send a color to the fragment shader in the form of a uniform; We can also send values from the vertex shader called **varyings**. Fragment shader will *interpolate* smoothly between vertex values (e.g. vertex color). 

------------------------------------------------------------------
# 3JS Docs on Types:

Vertex shader runs first. It receives **attributes**, calculates/manipulates position of each individual vertex, passes **varyings** to the fragment shader.

More on three types of variables:
- **Uniforms** are variables that have the same value for all vertices: lighting, fog, shadow maps are examples of uniforms. Accessible by both the vertex shader and the fragment shader.
- **Attributes** are variables associated with each vertex: vertex position, face normal, and vertex color, etc. *Only* accessible within vertex shader.
- **Varyings** are variables passed from vertex shader to the fragment shader. For each fragment, the value of each varying will be smoothly interpolated from the values of adjacent vertices.

Within the shader, uniforms and attributes act like constants; we can only modify their values by passing different values to the buffers from our JS.

---
# ShaderMaterial v. RawShaderMaterial

In 3JS, we have the ShaderMaterial or RawShaderMaterial to choose from. 