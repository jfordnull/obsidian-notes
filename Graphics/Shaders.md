Shader language depends on target environment. The two I've seen most regularly are:
- GLSL (OpenGL Shading Language)
- HLSL (High Level Shader Language, Direct3D's graphics language)
# Vertex Shader

Vertex shaders position the vertices of our geometry. We'll pass matrices describing vertex positions, mesh transformations, and camera information to the shader. The GPU follows the shader's instructions to project each "3D" vertex onto our 2D render space, or canvas. (GPU applies the shader to thousands of vertices in parallel.)

Two types of data:
- **Attributes**, e.g. individual vertex position, which differ per vertex
- **Uniforms**, e.g. camera transform, a mesh transform, etc., consistent across vertices
# Fragment Shader

Used to color each visible fragment of the geometry. We don't use attributes in the fragment shader. We can send a color to the fragment shader in the form of a uniform; We can also send values from the vertex shader called **varyings**. Fragment shader will *interpolate* between vertex values (e.g. vertex color). 