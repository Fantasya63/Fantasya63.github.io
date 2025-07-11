# Painter

**Type:** `ScriptableObject`

---

## Description

`Painter` is a ScriptableObject that defines brush settings used by the `PaintableManager` to paint onto `Paintable` surfaces. It includes both color and PBR properties and can be reused across multiple painting operations.

---

## Creation

You can create a new `Painter` asset via:

> `Assets > Create > Paintable > Painter`

This will create a new `.asset` file with default paint settings.

---

## Fields

### `public Color color`
The base color used when painting on a `Paintable` surface.
*Use an alpha value of zero to remove paint*

---

### `public float radius = 0.05f`
Controls the brush size in UV space.  
- Small values = fine detail  
- Large values = broader strokes

---

### `public float hardness = 0.5f`
Controls edge softness of the brush:
- `0` = completely soft (blurred edge)
- `1` = completely hard (sharp edge)

---

### `public float strength = 0.5f`
Intensity or opacity of the brush stroke.

---

### `public float metallic = 0.0f`
Sets the metallic value for the PBR (Physically Based Rendering) map:
- `0` = non-metallic (plastic/wood)
- `1` = fully metallic (aluminum/gold)

---

### `public float smoothness = 0.56f`
Defines how smooth or rough the surface is:
- `0` = rough/diffuse
- `1` = perfectly smooth/mirror-like

---

### `public float height = 1.0f`
Encodes displacement or bump height data in the PBR map.

---

## Usage

This object is passed into `PaintableManager.Paint()`:

```csharp
Painter myPainter = ...; // assigned via inspector or loaded as asset
PaintableManager.Instance.Paint(myPaintable, myPainter, uvPos);
```