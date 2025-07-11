# Screw

**Type:** `MonoBehaviour`  
**Inherits:** [`IInteractable`](./iinteractable.md)

---

## Summary

Represents a screw component in the build system. This class handles user interaction for screwing and unscrewing actions and visually animates the screw accordingly. Used in conjunction with `RemoveScrewsStep`.

---

## Requirements

- **Component Requirements:**  
  - `Collider`  
  - `Outline`  

---

## Serialized Fields

| Field            | Type          | Description                                                      |
|------------------|---------------|------------------------------------------------------------------|
| `screwModel`      | `GameObject`   | The visual model of the screw to be animated.                   |
| `drilledPos`      | `Transform`    | The position of the screw when fully inserted.                  |
| `undrilledPos`    | `Transform`    | The position of the screw when fully removed.                   |
| `drillDuration`   | `float`        | Time (in seconds) to fully screw or unscrew. Default is 3.0.    |

---

## Public Properties

| Property          | Type       | Description                                        |
|-------------------|------------|----------------------------------------------------|
| `IsActionable`     | `bool`     | True if the screw is currently interactable.       |
| `IsAssemble`       | `bool`     | True if the screw is being inserted (not removed). |

---

## Unity Events

| Event               | Description                                      |
|---------------------|--------------------------------------------------|
| `OnScrewFinished`   | Invoked when the screw finishes its operation.   |

---

## Public Methods

### `void OnActivateScrew(bool isAssemble, BuildableSocket socket)`

Activates the screw for user interaction. Sets the initial position of the screw model based on whether it's being assembled or disassembled.

### `void OnHover()`

Called when the player hovers over the screw. Handles input and progress for screwing/unscrewing. Progress increases while the "Action" input is held.

### `void OnHoverExit()`

Called when the player stops hovering over the screw. Resets the outline color.

---

## Notes

- **Uses `HoldableManager`** to ensure that screws can't be interacted with while holding an object.
- **Requires `BuildableManager`** for outline color configuration.
- Works in both assembly and disassembly modes by interpolating between positions.
