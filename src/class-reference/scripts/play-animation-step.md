# PlayAnimationStep

**Type:** `MonoBehaviour`  
**Inherits:** [`BuildableStep`](./buildable-step.md)

---

## Summary

`PlayAnimationStep` is a step used in a build sequence that plays an `AnimationClip` during assembly or disassembly of a buildable part. It attaches a temporary `Animation` component to the buildable, plays the appropriate animation clip, and finishes the step once the animation completes.

---

## Serialized Fields

| Field         | Type            | Description                                     |
|---------------|------------------|-------------------------------------------------|
| `removeClip`  | `AnimationClip` | The animation to play during disassembly.       |
| `insertClip`  | `AnimationClip` | The animation to play during assembly.          |

---

## Private Fields

| Field  | Type        | Description                                      |
|--------|-------------|--------------------------------------------------|
| `anim` | `Animation` | The temporary animation component used for playback. |

---

## Methods

### `protected override void OnStepActivated()`

- Adds an `Animation` component to the `buildable` GameObject.
- Adds the serialized clips under the names `"insert"` and `"remove"`.
- Starts the `StartAnimation()` coroutine.

### `protected override void OnStepFinished()`
- Destroys the temporary `Animation` component.


## Notes

- This step uses Unity's legacy `Animation` system (not `Animator`). This is suitable for simple, direct playback of clips.
- The animation component is added and removed at runtime to ensure clean reuse of buildables and minimal memory usage.

