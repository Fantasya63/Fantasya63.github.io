# UIManager

**Inherits:** `MonoBehaviour`

---

## Summary

The `UIManager` is a singleton MonoBehaviour responsible for holding UI elements. Currently, it is used by the [`ApplyThermalPaste`](../scripts/apply-thermal-paste-step.md) to get the progress slider and the continue text for the step

---

## Fields

### `public static UIManager Instance`

- Singleton instance of the UIManager.

---

### UI References

#### `public Slider pasteProgressSlider`

- A `UnityEngine.UI.Slider` that represents the thermal paste coverage progress.
- Expected to be updated during the `ApplyThermalPasteStep`.

#### `public TextMeshProUGUI pasteContinueText`

- A `TextMeshProUGUI` text element that prompts the user to press space to continue the apply thermal paste step when sufficient coverage is reached.

---
