# BaseHoldable

**Inherits:** `MonoBehaviour`  
**Type:** `Abstract Class`  
**Required Components:** `Collider, Outline`  

## Description

`BaseHoldable` is an abstract class that defines the core logic for objects that can be held and placed within a scene. It manages visuals through mesh duplication, validates placement using intersection detection, and provides hooks for derived classes to implement placement logic.

---

## Exported Properties

### `LayerMask placeAreaMask`
Mask used for raycasting against valid placement zones.

### `LayerMask intersectMask`
Mask used to detect potential intersections when attempting placement.

### `Vector3 placeOffset`
Positional offset applied when the object is placed.

### `Vector3 placeOffsetRotation`
Rotational offset applied when the object is placed.

### `Material placeMaterial`
Material used for visualizing a valid placement state.

### `Material intersectMaterial`
Material used for visualizing an invalid (intersecting) placement state.

---

## Public Members

### `Outline outline`
Outline component used to highlight the object when selected or held.

---

## Protected Members

### `float _placeRotation`
Optional rotation angle for placement.

### `GameObject visualizerInstance`
Instance used to display a mesh placeholder (ghost preview) when holding the object.

### `IntersectionDetector detector`
Component that checks for object intersection during placement.

---

## Virtual Methods

### `virtual void Awake()`
Initializes and caches the `Outline` component.

---

### `virtual bool CanHold() → bool`
Returns whether the object can currently be held. Override to add hold restrictions (e.g., item already installed). If not overwritten, this function always returns true.

---

### `virtual void Hold(Transform holderPosition)`
- Parents the object to the given holder transform.
- Zeros local position and rotation.
- Initializes a ghost visualizer for placement.

---

### `virtual bool Place(Vector3 position, Quaternion rotation) → bool`
Attempts to place the object at the specified world position and rotation.
- Fails if there is a collision (`detector.IsIntersecting`).
- Applies position and rotation with offset.
- Unparents the object from the holder.

---

## Abstract Methods

### `abstract bool OnCheckPlaceArea(Ray ray)`
Must be implemented by child classes. Called every frame by the holdable manager to check whether placement is valid based on a given ray.

---

## Example Usage

Create a class that inherits from `BaseHoldable`, and implement `OnCheckPlaceArea()`:

```csharp
public class PartHoldable : BaseHoldable
{
    private Buildable buildable;

    protected override void Awake()
    {
        base.Awake();
        buildable = GetComponent<Buildable>();
    }

    public override bool CanHold()
    {
        // Can only hold this item if it is not inserted
        return !buildable.IsInserted;
    }

    public override bool OnCheckPlaceArea(Ray ray)
    {
       
        // Check for sockets
        // etc
    }

}
```
sdasd
