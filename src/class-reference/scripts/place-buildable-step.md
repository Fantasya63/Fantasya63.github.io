# PlaceBuildableStep

**Type:** `MonoBehaviour`  
**Inherits:** [`BuildableStep`](./buildable-step.md), [`IInteractable`](./iinteractable.md)

---

## Summary

`PlaceBuildableStep` is a build step used in assembly/disassembly sequences where a part needs to be *placed* via an animation triggered by player interaction. It enables a collider for interaction, plays an animator trigger, and notifies the build system when the step is completed.

---

## Requirements

- Must be attached to a GameObject with a `BoxCollider`.
- Requires an `Animator` component (set via inspector).

---

## Serialized Fields

| Field            | Type        | Description                                                |
|------------------|-------------|------------------------------------------------------------|
| `animator`       | `Animator`  | Animator that plays the placement animation.              |
| `animatorTrigger`| `string`    | Name of the trigger parameter to invoke.                  |

---

## Private Fields

| Field     | Type       | Description                              |
|-----------|------------|------------------------------------------|
| `started` | `bool`     | Flag to ensure animation triggers only once. |
| `col`     | `Collider` | Cached `BoxCollider` for enabling/disabling interaction. |

---

## Notes

- The step automatically finishes when the animation completes.
- This step relies on Unity’s Animator system and is ideal for mechanical parts that visually move when placed.
- The outline logic includes a workaround for a known bug where outlines might get disabled unexpectedly.
