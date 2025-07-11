# Paintable

**Inherits from:** `MonoBehaviour`

## Description

The `Paintable` component manages the runtime-generated textures used for painting objects at runtime. These textures are applied to a specified `Renderer` and are used in shaders to display dynamic paint effects.

---

## Serialized Fields

### `Renderer rend`
The renderer whose material will be assigned the generated textures.  
**Note:** This must be assigned in the Inspector.

---

## Public Methods

### `RenderTexture GetColorMask()`
Returns the color mask `RenderTexture`.

### `RenderTexture GetPBRMap()`
Returns the PBR map `RenderTexture`.

### `Renderer GetRenderer()`
Returns the assigned `Renderer`.

---

## Dependencies

- **Shader Support:** The material assigned to `rend` must support `_ColorMaskTex` and `_PBRDetailsTex` properties.
- **PaintableManager:** Relies on `PaintableManager.TextureSize` to define the resolution of the generated textures.
- **Mesh UV2** The mesh that this script will use must have a UV2 texture coordinate to use as the uv for texture painting

---

## Example Use

```csharp
RenderTexture colorMaskTex = paintable.GetColorMask();
RenderTexture pbrDetailsTex = paintable.GetPBRMap();

// Do something with the textures...
```
