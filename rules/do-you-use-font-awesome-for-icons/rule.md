---
type: rule
title: Do you use Font Awesome for icons?
uri: do-you-use-font-awesome-for-icons
created: 2014-06-18T05:00:53.0000000Z
authors:
- id: 37
  title: Ben Cull
- id: 38
  title: Drew Robson

---

 ​





​​​​​​​​Bootstrap comes with a good font-based icon library to use in your web application, but there is an even better one you should use whenever you are using Bootstrap.​   ​  
When building a web application, it is common that you will need icons in the UI. Traditionally, this has been done with images (e.g. png, jpg) which leads to a lot of resource management.
![23-06-2014 11-20-02 AM.png](/PublishingImages/23-06-2014%2011-20-02%20AM.png)Figure: Bad example - using images for application icons
This is simplified if you are using Bootstrap, as it comes with a font-based icon library you can use in your web application. However, there is an even better third-party font-based icon library you should use when using Bootstrap.

Font Awesome provides scalable vector icons which can be customized purely through CSS and is completely free for commercial projects. This is great if you’re tight on implementation deadlines, but is no replacement for a specifically designed icon set. However if you need generic icons in a hurry, then use Font Awesome.

Using it on your project is easy, just add the following stylesheet to your app:​


```
<link href="//netdna.bootstrapcdn.com/font-awesome/3.2.1/css/font-awesome.css" rel="stylesheet" />​
```


Then you have access to over 350 icons. Here are a few commonly used ones:

​​​*​​​**​​​*​
Figure: Examples of Font Awesome icons
​​​The HTML is easy, e.g. &lt;i class="fa fa-trash-o"&gt;&lt;/i&gt;​ to add the above trashbin icon.

​You can also download and reference Font Awesome locally.
![23-06-2014 11-08-06 AM.png](/PublishingImages/23-06-2014%2011-08-06%20AM.png)Figure: After adding Font Awesome from NuGet, two lines of code add the below icon​![18-06-2014 2-33-45 PM.png](/PublishingImages/18-06-2014%202-33-45%20PM.png)Figure: A 5x scaled paper plane icon has been added to my Web Application
You can get Font Awesome from NuGet or        [http://fortawesome.github.io/Font-Awesome/](http&#58;//fortawesome.github.io/Font-Awesome/).​

Also check out Eric Phan's blog for more info: [http://ericphan.net/blog/2013/10/15/javascript-corner-font-awesome​​](http&#58;//ericphan.net/blog/2013/10/15/javascript-corner-font-awesome).
 ​​
