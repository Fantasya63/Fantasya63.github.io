# ShowObjectStep

**Inherits:** [`BuildableStep`](./buildable-step.md)

---

## Summary

A simple step that "reveals" a GameObject by translating it upward in the world space. Commonly used to simulate objects appearing in a build sequence.

---

## Serialized Fields

| Field           | Type        | Description                                        |
|------------------|-------------|----------------------------------------------------|
| `objectToShow`   | `GameObject` | The object to be revealed when this step activates.|

---

## Notes

- This is the counterpart of [`HideObjectStep`](./hide-object-step.md), which hides objects by moving them downward.
- The translation is hardcoded and not animated — it's purely a positional jump.
- Assumes the object was previously moved down (e.g. hidden offscreen).

---
