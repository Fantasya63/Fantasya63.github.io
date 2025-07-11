# HideStep

**Inherits:** [`BuildableStep`](./buildable-step.md)

## Description

`HideStep` is a [`BuildableStep`](./buildable-step.md) that immediately hides the assigned `buildable` by translating it far downward, effectively removing it from view. Use this step instead of the [`HideObjectStep`](./hide-object-step.md) when u want to hide the buildable as the [`HideObjectStep`](./hide-object-step.md) cant access the currently inserted buildable

---

## Overridden Methods

### `override void OnStepActivated()`
Moves the `buildable` GameObject downward by a large amount and finishes the step immediately.