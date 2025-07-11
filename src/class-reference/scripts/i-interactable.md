# IInteractable

**Type:** `Interface`

## Description

`IInteractable` defines the contract for objects that can be interacted with via hovering behavior, such as outlines or tooltips.

Classes that implement this interface are expected to respond to player hover events, typically through raycasting from a cursor or camera.

---

## Methods

### `void OnHover()`
Called when the player begins hovering over the object.  
Common behavior includes:
- Enabling visual outlines
- Highlighting
- Displaying UI or tooltips

---

### `void OnHoverExit()`
Called when the player stops hovering over the object.  
Typically used to:
- Disable outlines
- Hide hover-related UI
- Revert visual effects

---


## Example

```csharp
public class MyInteractable : MonoBehaviour, IInteractable
{
    public void OnHover()
    {
        Debug.Log("Hovering over me!");
    }

    public void OnHoverExit()
    {
        Debug.Log("No longer hovering.");
    }
}
