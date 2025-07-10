# AnimateBuildableOnClickStep

**Inherits:** `BuildableStep`  
**Implements:** `IInteractable`  
**Required Components:** `Collider`  

## Description

`AnimateBuildableOnClickStep` is a BuildableStep that will animate the current buildable (pc part) that is currently attached to this step's assigned BuidableSocket. The animation to be played is controlled by the  ```animationTrigger``` string.

---

## Properties
### Serialized Private
### `string animatorTrigger`

The name of the trigger parameter in the Animator that will be activated when this step starts.

## Usage Notes

- Make sure an `Animator` component is attached to the buildable’s GameObject.
- This step relies on Unity's `Input.GetButtonDown("Action")` to trigger.
- The outline is force-enabled due to a bug that causes it to randomly disable.

---

## Example
Setup the step
![Setup the trigger name](../../../assets/animate-buildable-on-click/example.png)

Apply step to the sockets or buidables
![Apply the step to the socket](../../../assets/animate-buildable-on-click/example2.png)