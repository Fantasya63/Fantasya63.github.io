# ClickAndAnimateStep

**Inherits:** [`BuildableStep`](./buildable-step.md)  
**Implements:** [`IInteractable`](./iinteractable.md)  

## Description

`ClickAndAnimateStep` is a `BuildableStep` that waits for player interaction (a button press) while hovering, then triggers an animation using an assigned `Animator`. Once the animation is complete, the step is considered finished.

This step enables interactive visual feedback, suitable for clicks that cause objects to move, rotate, or open (e.g., CPU socket lever)

---

## Serialized Fields

### `Animator animator`
The Animator component that controls the animation for this step. Must not be null.

### `string animatorTrigger`
The name of the Animator trigger parameter that starts the animation.

### `Collider clickColider`
The collider used to detect hover and clicks. This is enabled only when the step is active.

### `Outline[] outlines`
An array of outline components that are highlighted when the player hovers over the step.

---

## Public Methods

### `void OnHover()`
Called while the user is hovering over the clickable step.  
- Updates outline color to hover color.
- Triggers the animation and starts the coroutine if `Action` input is pressed.

---

### `void OnHoverExit()`
Called when the user stops hovering.  
- Resets all outlines to default color.

---

## Inherited Methods

### `override void OnStepActivated()`
Called when this step is activated by the socket system.  
- Enables click collider.
- Enables outlines and sets their color.

---

### `override void OnStepFinished()`
Called when the animation finishes and the step is complete.  
- Disables collider and outlines.
