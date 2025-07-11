# Issues

- Prevent the user from initiating another assembly/dissassembly when doing actions that involve zooming in to prevent the current action to be taken out of the zoom mode.

- rework on the ray casting objects to be able to enable outlines when hovering over an object. The current implementation's raycasts are in different places and interferes with the other, competing as to what to outline so it's been disabled for now

- When inserting a buildable, if the buldable has sockets, take the socket's (being inserted into) locking and required assets and add it to the buildable's sockets to prevent interacting with the buldable's socket when it shouldnt be able to

- Currently, there are no buildableSocket for the PSU.

