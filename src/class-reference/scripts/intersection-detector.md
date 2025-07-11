# IntersectionDetector

**Inherits:** `MonoBehaviour`  
**Required Components:** `Collider`

## Description

`IntersectionDetector` is a utility script used to detect whether a GameObject intersects with other objects within a specified `LayerMask`. It is commonly used for visual placement validation when positioning objects in 3D space (e.g., ghost objects, build previews).

When an intersection is detected, the object's material changes to indicate a collision (typically red). When no intersection is found, it uses a different material (typically green or transparent).

---

## Properties

### `Material placeMaterial`
The material applied to the object when **no intersection** is detected.

### `Material intersectMaterial`
The material applied to the object when an **intersection** is detected.

### `LayerMask mask`
Layer mask used to define which objects should be considered during intersection checks.

### `bool IsIntersecting` *(read-only)*
Returns `true` if the object is currently intersecting with another object in the specified mask.

---

## Example Use Case

Used as part of the `BaseHoldable` system to give visual feedback while placing objects:

```csharp
if (intersectionDetector.IsIntersecting)
{
    // Show red placement feedback
}
else
{
    // Show green placement feedback
}
