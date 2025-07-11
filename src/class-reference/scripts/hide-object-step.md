# HideObjectStep

**Inherits:** [`BuildableStep`](./buildable-step.md)

## Description

`HideObjectStep` is a `BuildableStep` that instantly hides a specified `GameObject` by moving it far out of view.  
It is intended for use in disassembly steps or animations where a part must visually disappear without disabling it.

---

## Serialized Fields

### `GameObject objectToHide`
The GameObject that will be hidden when this step is activated.  
Must not be null.

---

## Overridden Methods

### `override void OnStepActivated()`
Immediately hides the object by translating it downward and finishes the step.
