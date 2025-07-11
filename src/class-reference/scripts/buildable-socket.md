# BuildableSocket

**Inherits:** `MonoBehaviour`  
**Implements:** `IInteractable`

## Description

`BuildableSocket` is a modular socket for inserting and managing `Buildable` components. It controls assembly and disassembly logic using a sequence of `BuildableStep`s and ensures part compatibility through `PartType` or specific `PART_ID`s.  
It also coordinates interaction rules based on dependency or blocking sockets.

---

## Properties

### `bool isActionStarted`
Returns `true` if a build or disassemble action is in progress.

### `Transform GetPartHolderTransform`
Returns the transform where inserted parts will be parented.

### `bool HasCustomOrientation`
Indicates if this socket applies a custom rotation offset to inserted parts.

### `Vector3 CustomRotation`
Returns the custom rotation offset used when placing buildables in the socket.

---

## Public Methods

### `bool IsCompatible(Buildable buildable)`
Checks if the specified `Buildable` is compatible with this socket, based on `acceptedPartType` or explicitly allowed `PART_ID`s.

---

### `bool CanAttach(Buildable buildable)`
Checks if a `Buildable` can be inserted into this socket:
- Must be compatible.
- Socket must not be occupied.
- Socket's required and locking sockets must be satisfied.

---

### `bool AttachBuildable(Buildable buildable)`
Attempts to insert the given `Buildable` into the socket. Returns `true` if successful.  
Triggers the **assembly** sequence via `StartAction(true)`.

---

### `bool RemoveBuildable()`
Attempts to remove the connected `Buildable` from the socket. Returns `false` if no buildable is present.  
Triggers the **disassembly** sequence via `StartAction(false)`.

---

### `bool IsOccupied()`
Returns `true` if a `Buildable` is currently inserted.

---

### `bool CanInteract()`
Checks whether this socket is available for interaction:
- Returns `false` if any **locking sockets** are occupied.
- Returns `false` if any **required sockets** are unoccupied.

---

### `void OnHover()`
Invoked by `BuildableManager` when the user hovers over this socket.  
- Displays the outline of the connected part (if available).
- Fires `OnHoverEvent`.

---

### `void OnHoverExit()`
Called when the hover ends.  
- Disables the outline of the connected buildable (if present).
- Fires `OnHoverExitEvent`.

---

## Signals

### `UnityEvent OnHoverEvent`
Fired when a user hovers over this socket.

### `UnityEvent OnHoverExitEvent`
Fired when the user stops hovering this socket.

