# TransitionCameraStep

**Inherits:** `BuildableStep`

---

## Summary

`TransitionCameraStep` is a `BuildableStep` that smoothly transitions the main camera to a specified position and rotation using linear interpolation over a set duration. This is typically used to guide the player’s view during critical build steps.

---

## Serialized Fields

### `Transform desiredCameraTransform`

- The target position and rotation the camera will transition to.

### `float lerpTime`

- The total duration (in seconds) of the camera transition.
- Default: `1.0f`

---

## Notes

- Temporarily sets the game mode to `RestrictedCam` via `GameManager.SetGameMode` (TODO: Change this when integrating with other game modes).
- This step completes automatically after the transition ends.
