---
type: rule
title: Do you use the designer for all visual elements?
uri: do-you-use-the-designer-for-all-visual-elements
created: 2009-04-28T02:20:39.0000000Z
authors:
- id: 1
  title: Adam Cogan
- id: 17
  title: Ryan Tee

---


The designer should be used for all GUI design. Controls will be dragged and dropped onto the form and all properties should be set in the designer, e.g.

- Labels, TextBoxes and other visual elements
- ErrorProviders
- DataSets (to allow data binding in the designer)


Things that do not belong in the designer:

- Connections
- Commands
- DataAdapters


However, and **DataAdapter** objects should not be dragged onto forms, as they belong in the business tier. Strongly typed **DataSet** objects should be in the designer as they are simply passed to the business layer. Avoid writing code for properties that can be set in the designer.
![](BadDesigner.gif) Bad example - Connection and Command objects in the Designer ![](GoodDesigner.gif) Good example - Only visual elements in the designer
