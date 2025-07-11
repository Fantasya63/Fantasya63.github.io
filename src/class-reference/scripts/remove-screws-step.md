# RemoveScrewsStep

**Type:** `MonoBehaviour`  
**Inherits:** [`BuildableStep`](./buildable-step.md)

---

## Summary

`RemoveScrewsStep` is a build step responsible for managing the interaction and removal of multiple `Screw` objects. The step completes only when all screws are unscrewed or screwd. This step is bidirectional, meaning it can be used to unscrew or screw in screws depending if we are assembling or disassembling.

---

## Serialized Fields

| Field     | Type      | Description                              |
|-----------|-----------|------------------------------------------|
| `screws`  | `Screw[]` | Array of screws required to be removed.  |

---


## Notes

- Each `Screw` object must call its `OnScrewFinished` event once fully removed or screwed.
- Designed to work in both `isAssemble` and disassembly modes depending on context.
- Screws should handle their own interaction (e.g., clicking).
