# Adding Sockets

---

## Setup

You can add sockets by adding the BuildableSocket Component to a gameObject. This requires a collider to be present.

![](../../../assets/socket/socket-setup.png)


*Remember to set the gameObject's layerMask to Sockets*

![](../../../assets/socket/socket-layer-set.png)

## Adding steps

- Create a gameobject to hold the steps for this socket.
- Drag and drop the steps to their respected arrays.

when you're done, it should look something like this:

![](../../../assets/socket/steps-child.png)
![](../../../assets/socket/steps-array.png)

## Accepted part types

Next, we indicate what part type is accepted by the socket. This can be done through the `Accepted Part Type` dropdown in the inspector. However, If this socket only takes a specific part such as a case panel slot only accepting its respective panel part, you can indicate this in the `Accepted Part ID`. If this is set, the system will ignore whatever the value `Accepted Part Type` is and only allows the indicated part to be inserted.


![](../../../assets/socket/accepted-parts.png)

## Part and Steps

- Create a gameObject to hold the buildable part when it is inserted. After that, assign the created gameObject to the part holder in the inspector as well as the steps holder you created a few steps ago.


![](../../../assets/socket/part-holder-type.png)

## Connected Part type

If this socket has a part connected to it by default such as a case panel, add the case panel as a child of the part holder u created then drag and drop the part to the connectedPart slot


![](../../../assets/socket/connected.png)


## Custom Rotation

If the part's orientation is off when being inserted, this may be because this socket's orientation is different from what it would generally be. You can check this by adding a part in the partHolder and clearing it's rotation. If the part is in the wrong orientation, check the `custom rotation` box and indicate the rotation offsets below



![](../../../assets/socket/custom-rot.png)

With all the steps provided, you now have a functionally buildableSlot ready to insert some parts
