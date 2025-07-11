# PaintableManager

**Namespace:** *(None)*  
**Inherits from:** `MonoBehaviour`

## Description

`PaintableManager` is a singleton component responsible for managing dynamic texture painting on objects via GPU compute shaders. It provides painting and surface property modification functionality, as well as coverage analysis.

---

## Constants

### `public const int TextureSize = 128`
Defines the resolution for both color and PBR maps. This is shared across all paintable surfaces.

---

## Serialized Fields

### `ComputeShader painterCompute`
Compute shader responsible for applying paint effects (color + PBR data).

### `ComputeShader contributionShader`
Compute shader used to calculate the painted surface's coverage.

### `Texture2D contribFacTex`
A 2D texture that acts as a contribution factor lookup used during the coverage analysis.
The data is read from the Red Channel of the texture

---

## Public Methods

### `void Paint(Paintable paintable, Painter painter, Vector2 pos)`
Paints on a given `Paintable` at UV coordinates `pos`, using brush parameters defined in the `Painter`:

**Parameters:**
- `paintable`: The object to paint on.
- `painter`: The brush configuration.
- `pos`: The UV coordinates of the brush stroke.

---

### `float GetCoverage(Paintable paintable)`
Gets the current coverage of the color mask on the paintable object.

---

## Example Use

```csharp
// Paint something at a UV location
PaintableManager.Instance.Paint(paintableObj, painterConfig, uvCoords);

// Get how much surface is covered
float coverage = PaintableManager.Instance.GetCoverage(paintableObj);
