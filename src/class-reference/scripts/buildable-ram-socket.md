# BuidableRamSocket

**Inherits:** `BuildableSocket`  


## Description

`BuidableRamSocket` is a specialized version of `BuildableSocket` designed for RAM components. It adds animation signaling functionality by invoking a boolean event (`AnimatorRamEvent`) whenever assembly or disassembly occurs. This event is used to signal the clip to play the open animation when dissassembling.

---

## Signals

### `AnimatorRamEvent OnAnimatorRamEvent`
A UnityEvent with a `bool` parameter that fires when the RAM is inserted or removed.  
- `true` = assembled  
- `false` = disassembled

---

## Methods

### `void OnAnimatorRamAssemble()`
called by an animation then invokes the `OnAnimatorRamEvent` with `true`.  
Used to signal that the RAM is being assembled.


### `void OnAnimatorRamDisassemble()`
called by an animation then invokes the `OnAnimatorRamEvent` with `false`.  
Used to signal that the RAM is being disassembled.
