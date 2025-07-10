# ApplyThermalPasteStep

**Inherits:** `BuildableStep`  

## Description

`ApplyThermalPasteStep` simulates the process of applying and removing thermal paste on a processor during PC assembly or disassembly.

---

## Properties

### `LayerMask processorMask`
Layer mask for detecting valid processor surfaces during raycasting.

### `GameObject thermalPastePrefab`
Prefab representing the visual of applying thermal paste.

### `GameObject removePastePrefab`
Prefab representing the visual of removing thermal paste.

### `Painter addPastePainter`
Painter used for applying thermal paste.

### `Painter removePastePainter`
Painter used for removing thermal paste.

### `Texture2D contributionFactor`
Texture used to calculate contribution of painted areas toward total coverage. The data is read at the red channel of the cpu and is used as weight in the contribution of the pixels

### `float requiredThermalPasteCoverage`
Required coverage value to complete the step when assembling.

### `float epsilonCoverage`
Threshold value for minimal coverage when removing paste during disassembly.

---

## Example Usage
---