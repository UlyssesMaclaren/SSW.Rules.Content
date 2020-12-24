---
type: rule
archivedreason: 
title: Controls - Do you use a ToolTip to show the full text of hidden ListView data?
guid: c025f79b-669a-4be5-8ece-28755c263c01
uri: controls-do-you-use-a-tooltip-to-show-the-full-text-of-hidden-listview-data
created: 2012-11-27T09:14:27.0000000Z
authors:
- id: 1
  title: Adam Cogan
related: []
redirects: []

---

When you can't see all the text for an item in a ListView you need to expose the full text via a ToolTip.

<!--endintro-->

[[badExample]]
| ![Users can't see all the text and the ListView doesn't use a Tooltip](../../assets/ListViewWithoutToolTip.gif)
[[goodExample]]
| ![Users can't see all the text, but the ListView shows all the text via a Tooltip](../../assets/ListViewWithToolTip.gif)
The code to do this is:

private ListViewItem hoveredItem;
 private void listView1\_MouseMove(object sender, MouseEventArgs e)
 { 
 ListView lv = (ListView) sender; 
 ListViewItem item = lv.GetItemAt(e.X, e.Y);
 int columnIndex = 1;
 if (item != hoveredItem)
 { 
 hoveredItem = item; 
 if (item == null) 
 { 
 toolTip1.SetToolTip(lv, ""); 
 } 
 else 
 { 
 // Make sure the mouse hovered row has the subitem 
 if (item.SubItems.Count > columnIndex)
 { 
 toolTip1.SetToolTip(lv, item.SubItems[columnIndex].Text);
 } 
 else 
 { 
 toolTip1.SetToolTip(lv,""); 
 } 
 } 
 } 
 }
