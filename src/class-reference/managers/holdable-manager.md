# HoldableManager

**Inherits:** `MonoBehaviour`

## Description

`HoldableManager` handles the logic for picking up (`Hold`) and placing (`Place`) objects that derive from `BaseHoldable`.  
It uses raycasting to detect nearby holdable objects and manages the currently held item and its visual feedback.

---

## Properties

### `static HoldableManager Instance`
Singleton instance of the manager.

### `BaseHoldable currentlyHolding`
The object that is currently held by the player. `null` if not holding anything.

### `float rotationSensitivity`
Rotation sensitivity used when manipulating holdable objects. Default is `300.0f`.

---

## Serialized Fields

### `LayerMask holdableMask`
The layer mask used to raycast against holdable objects.

### `Transform _holdablePosition`
The transform where held objects are visually placed (typically in front of the player).

---

## Methods

### `bool Hold(BaseHoldable holdable)`
Attempts to hold the given object. Returns `true` if successful.

Conditions:
- Must not already be holding another object.
- The object must return `true` for `CanHold()`.

---

### `void RemoveHold()`
Clears the currently held object.

---

### `bool CheckForHoldable(Ray ray)`
Performs a raycast using the provided ray to detect a `BaseHoldable` object.
- Enables or disables outlines based on detection.
- Triggers `Hold()` when the "Hold" input is pressed.

Returns `true` if a valid holdable was found and (optionally) held.

---

## Input Actions

- `Input.GetButtonDown("Hold")` → Used to pick up a holdable object.

---

## Example Usage

```csharp
if (HoldableManager.Instance.currentlyHolding == null)
{
    HoldableManager.Instance.Hold(myHoldable);
}
