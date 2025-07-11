# PartHoldable

**Type:** `MonoBehaviour`  
**Inherits:** [`BaseHoldable`](./base-holdable.md)

---

## Summary

`PartHoldable` is a component attached to objects that can be held and placed into `BuildableSocket`s. It is used on buildables that can be inserted into a PC build, such as CPU, GPU, RAM, etc.

This class handles logic for picking up, checking for valid sockets, rotating during placement, and placing either into sockets or on flat surfaces like a table.

---

## Dependencies

- Requires a [`Buildable`](./buildable.md) component on the same GameObject.
- Interacts with:
  - [`HoldableManager`](./holdable-manager.md)
  - [`BuildableSocket`](./buildable-socket.md)
  - [`GameManager`](./game-manager.md)

---

## Serialized Fields

- `placeAreaMask` – the mask used to detect where the object can be placed.

---

## Methods

### `protected override void Awake()`

Initializes the `buildable` reference by calling `GetComponent<Buildable>()` after base initialization.

---

### `public override bool CanHold()`

Returns `true` if the part is **not inserted** (i.e. available to be held).