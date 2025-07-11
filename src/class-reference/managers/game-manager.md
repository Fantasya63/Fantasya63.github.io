# GameManager

**Inherits:** `MonoBehaviour`  
**Type:** Singleton

## Description

`GameManager` handles core game state and global settings, such as the current game mode and player interaction range.  
It follows the Singleton pattern to ensure only one instance is active at a time.

---

## Enums

### `GAMEMODE`
Defines the current gameplay mode:
- `Tutorial`
- `Challenge`
- `Free`
- `Roam`
- `RestrictedCam`

---

## Properties

### `static GameManager Instance`
Returns the active instance of the `GameManager`.  
Ensures only one manager exists in the scene.

---

### `GAMEMODE GameMode`
Returns the current active game mode.

---

### `float reachDistance`
Maximum raycast range used for player interaction (default: `150.0f`).

---

## Signals

### `GameModeEvent OnGameModeChanged`
Triggered when the game mode changes.  
Passes the new `GAMEMODE` as a parameter.

---

## Public Methods

### `void SetGameMode(GAMEMODE gameMode)`
Sets the current game mode.

If `RestrictedCam` is set:
- Unlocks the mouse cursor.
- Makes the cursor visible.

Also triggers `OnGameModeChanged`.
