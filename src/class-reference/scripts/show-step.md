# ShowStep

**Type:** `ShowStep : BuildableStep`

---

## Summary

A `BuildableStep` that reveals the associated `Buildable` object by moving it upward in world space. Typically used in assembly sequences where an object needs to visually appear or re-enter the scene.


---

## Notes

- This step is the reverse of [`HideStep`](./hide-step.md), which hides the buildable by translating it downward.
- There is no animation involved; the movement is instantaneous.
- Assumes the object was hidden previously by being moved out of view.
