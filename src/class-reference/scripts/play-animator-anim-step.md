# PlayAnimatorAnimStep

**Type:** `MonoBehaviour`  
**Inherits:** [`BuildableStep`](./buildable-step.md)

---

## Summary

`PlayAnimatorAnimStep` is a step that triggers an animation on a Unity `Animator` and waits for it to finish (or waits for a custom duration) before completing the build step. 

---

## Serialized Fields

| Field             | Type      | Description                                                                 |
|------------------|-----------|-----------------------------------------------------------------------------|
| `animator`       | `Animator` | The Animator component used to play the animation.                         |
| `triggerName`    | `string`   | The name of the trigger parameter to activate on the Animator.             |
| `customWaitSeconds` | `bool`     | If true, ignores animation duration and uses `waitTillFinish` instead.      |
| `waitTillFinish` | `float`    | Time in seconds to wait if `customWaitSeconds` is enabled.                 |

---

## Methods

### `protected override void OnStepActivated()`

- Called when this step becomes active in a build process.
- Starts the `playAnimation()` coroutine.

### `private IEnumerator playAnimation()`

- Triggers the animation using the specified trigger.
- If `customWaitSeconds` is `true`, waits the specified time then finishes.
- Otherwise, waits until the triggered animation finishes playing before calling `FinishStep()`.

---

## Notes

- Uses the Unity `Animator` component (Mecanim system).
- Supports both event-driven and time-driven behavior via `customWaitSeconds`.
- `AnimatorStateInfo.normalizedTime` is used to determine animation completion.

