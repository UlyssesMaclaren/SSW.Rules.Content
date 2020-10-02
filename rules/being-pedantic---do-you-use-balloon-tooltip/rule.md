---
type: rule
title: Being Pedantic - Do you use balloon tooltip?
uri: being-pedantic---do-you-use-balloon-tooltip
created: 2012-11-27T09:23:38.0000000Z
authors: []

---

The standard tooltip is a rectangle, so the tool tip for the control can be misleading. While, the balloon tooltip has an arrow pointing to the destination control, which is clearer for users.
 
![ Standard tooltip.](../../assets/BadTooltip.gif)

![ Balloon tooltip.](../../assets/GoodTooltip.gif)

To implement you can:

1. Set the standard Tooltip's property IsBalloon true or
2. Use EdwardForgacs' balloon tooltip control.
