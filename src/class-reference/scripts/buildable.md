# Buildable

**Inherits:** `MonoBehaviour`  
**Required Components:** `PartHoldable`, `Collider`, `Outline`

## Description

`Buildable` represents a modular PC component (e.g., CPU, GPU, Fan) that can be held, inserted into sockets, assembled, and disassembled. It handles its own placement logic and manages related assembly/disassembly steps and visual feedback.

---

## Enums

### `PART_ID`
Unique identifiers for specific parts:

- `AsusA21MeshTGBlack`,
- `ASUSA21MeshTGBlackFrontPanel`,
- `ASUSA21MeshTGBlackBackPanel`,
- `ASRockZ590M`,
- `CorsairHD120RGB`,
- `CVNGuardianDDR416GB`,
- `DeepCoolMF120`,
- `DeepCoolDCTF120S`,
- `SeagateBarracudaHDD1TB`,
- `i9_10900KF`,
- `GIGABYTE_Z590_VISION_G`,
- `ADATA_XPG_SX6000_M2_1TB`,
- `NVIDIA_GTX_1060`,
- `ARCTIC_COOLING_FREEZER_I35_ARGB`,

### `PartType`
Defines the category of the part:

- `Processor`,
- `Motherboard`,
- `Memory`,
- `GraphicsCard`,
- `Storage`,
- `PowerSupply`,
- `Fan`,
- `AirCooler`,
- `Case`,
- `Panels`,
- `None`

---

## Signals

### `UnityEvent OnBuildableDissassembled`
Invoked when the part is disassembled from a socket.

---

## Public Properties

### `PART_ID partID`
The unique identity tag for this specific PC part.

### `PartType partType`
The general type category for this part.

### `BuildableStep[] assemblySteps`
The sequence of steps required to assemble this part.

### `BuildableStep[] disassemblySteps`
The steps necessary to disassemble this part.

### `bool IsInserted`
(Readonly) Returns whether the buildable is currently inserted into a socket.

### `Outline outline`
The visual outline component for highlighting this object.

---

## Public Methods

### `virtual bool CanInsert(BuildableSocket socket)`
Returns `true` if this part is allowed to be inserted.  

---

### `void InsertToSlot(Transform slotHolder, Quaternion rot)`
Parents the buildable to a given socket location, applies positioning, and handles optional offset adjustments.

---

### `void OnAssembled()`
Marks this buildable as inserted.

---

### `void OnDisassembled()`
Marks the buildable as disassembled then makes the player hold the object
- Triggers `OnBuildableDissassembled` event


---

## Example

![Example usage of buildable](../../../assets/buildable/example.png)