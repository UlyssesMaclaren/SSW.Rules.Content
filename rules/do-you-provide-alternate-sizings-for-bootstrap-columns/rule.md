---
type: rule
title: Do you provide alternate sizings for Bootstrap columns?
uri: do-you-provide-alternate-sizings-for-bootstrap-columns
created: 2014-06-18T05:04:12.0000000Z
authors:
- id: 37
  title: Ben Cull
- id: 38
  title: Drew Robson

---

 ​​​​​​Bootstrap provides a powerful, responsive layout with its rows and columns. 
The common way to use Bootstrap's layout system is to create a basic grid which will appear as horizontal columns on the desktop but then stack on a smaller screen such as mobiles. This is done with a single set of .col-md-\* classes.
![](/PublishingImages/23-06-2014%2012-47-33%20PM.png)Figure: Bad example - create the default stacking layout with Bootstrap![23-06-2014 1-04-08 PM.png](/PublishingImages/23-06-2014%201-04-08%20PM.png)Figure:​ Bad example - the default stacking behavior on small devices
Did you know you can have more control over the responsive layout by including multiple column classes? The ability to control the layout across multiple screen sizes is a powerful tool within Bootstrap. For example, if you don't want your columns to stack on smaller devices, use the smaller grid classes by adding additional column classes (e.g. .col-xs-\* .col-sm-\*) to the respective &lt;div&gt;s.
![23-06-2014 12-45-30 PM.png](/PublishingImages/23-06-2014%2012-45-30%20PM.png)Figure: Good example - add additional column classes to your columns![23-06-2014 1-14-39 PM.png](/PublishingImages/23-06-2014%201-14-39%20PM.png)​Figure: Good example - On a smaller device, these columns now arrange horizontally as desired
