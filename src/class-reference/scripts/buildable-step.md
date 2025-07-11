# BuildableStep

**Inherits:** `MonoBehaviour`  
**Type:** Abstract Base Class

## Description

`BuildableStep` is the base class for all individual steps in the assembly and disassembly process of a `Buildable`.  
It manages step activation, progress tracking, and signals when the step is completed.

Each subclass of `BuildableStep` defines how the step is visually or logically executed (e.g., clicking a part, animating a component, applying paste).

*The definition of a BuildableStep is intentionally general sothat it can encompass any step you may want to implement. You just have to override `OnStepActivated` as the step's entry point, `OnStepFinished` as the exit point, and all you have to do to let the system know this step is finished is call `FinishStep()`*

---

## Properties

### `bool isLocked`
Indicates whether the step is currently locked (i.e., inactive).  
Set to `false` when the step is running, and `true` when it completes.

---

## Public Methods

### `virtual void ActivateStep(Buildable buildable, BuildableSocket socket, bool isAssemble)`
Initializes the step:
- Locks the step from reactivation.
- Stores references to the associated `Buildable`, `BuildableSocket`, and `isAssemble` mode.
- Triggers the `OnStepActivated()` lifecycle hook.

---

### `UnityEvent OnBuildableStepCompleted`
Fires when the step is finished (via `FinishStep()`).

---

### `UnityEvent OnBuildableStepStarted`
Should be invoked by derived classes when their step logic officially starts (e.g., user begins interaction or animation begins).

---

## Protected Methods

### `virtual void OnStepActivated()`
Called internally when the step is activated.  
Override in child classes to begin step-specific logic.

---

### `virtual void OnStepFinished()`
Called after the step is marked complete.  
Override in child classes for cleanup logic or effects.

---

### `void FinishStep()`
Marks the step as completed:
- Sets `isLocked = true`.
- Calls `OnStepFinished()`.
- Invokes `OnBuildableStepCompleted`.

---

## Example Usage (Subclass)

```csharp
public class ClickStep : BuildableStep
{
    protected override void OnStepActivated()
    {
        OnBuildableStepStarted.Invoke();
        // Wait for user click to finish step
    }

    void OnUserClick()
    {
        FinishStep(); // Triggers complete
    }
}
