# MoveObjectStep

**Inherits:** [`BuildableStep`](./buildable-step.md)

## Description

`MoveObjectStep` is a type of `BuildableStep` that moves a specific object in the scene by a given offset. It supports both assembling and disassembling actions, applying the offset in reverse for assembling and forward for disassembling.

---

## Serialized Fields

### `Vector3 movePosition`
The amount and direction by which to move the object during disassembly. The inverse of this is applied during assembly.

### `Transform objectToMove`
The specific `Transform` that will be moved during the step.