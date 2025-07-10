# Adding Sockets

---

## Setup

You can add sockets by adding the BuildableSocket Component to a gameObject. This requires a collider to be present.

![](../../../assets/socket/socket-setup.png)


*Remember to set the gameObject's layerMask to Sockets*

![](../../../assets/socket/socket-layer-set.png)

## Adding steps

- Create a gameobject to hold the steps for this socket.
- create gameobjects to hold the steps for assembling and disassembling.
- Drag and drop the steps to their respected arrays.

when you're done, it should look something like this:

![](../../../assets/socket/steps-child.png)
![](../../../assets/socket/steps-array.png)

## Accepted part types

Next, we indicate what part type is accepted by the socket. This can be done through the `Accepted Part Type` dropdown in the inspector. However, If this socket only takes a specific part such as a case panel slot only accepting its respective panel part, you can indicate this in the `Accepted Part ID`. If this is set, the system will ignore whatever the value `Accepted Part Type` is and only allows the indicated part to be inserted.


![](../../../assets/socket/accepted-parts.png)