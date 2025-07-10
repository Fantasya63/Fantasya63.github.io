# BuildableManager

**Inherits:** `MonoBehaviour`  

## Description

`BuildableManager` handles global interaction logic with buildable objects and sockets in the scene. It manages hover states, click actions, and outline highlighting for all `IInteractable` objects and `BuildableSocket`s within the player's reach.


*Note: Ensure this manager is loaded first before any ordinary gameObjects. this can be done by changing the script excecution order in the editor*

---

## Singleton

### `static BuildableManager Instance`
Singleton reference to the current `BuildableManager`.

---

## Public Fields

### `Color outlineColor`
Default color used for object outlines.

### `Color outlineHoverColor`
Color used for outlines when the object is hovered.

## Serialized private fields

### `LayerMask socketMask`
The LayerMask of the buildable sockets

### `LayerMask interactableMask`
The LayerMask of all interactables

---

## Private Methods

### `BuildableSocket RayCastClosestValidSocket(Ray ray)`

- Performs a `RaycastAll` with the `socketMask` and finds the nearest `BuildableSocket` that is currently **occupied**.
- Returns the closest matching socket or `null` if none are found.

---

## Example Usage

![](../../../assets/buildable/buildable-manager-example.png)