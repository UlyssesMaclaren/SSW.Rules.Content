---
type: rule
title: Do you use content editor web part with care?
uri: do-you-use-content-editor-web-part-with-care
created: 2009-11-02T23:32:03.0000000Z
authors:
- id: 8
  title: John Liu

---

 This field should not be null (Remove me when you edit this field).   However, there is a scary hidden trap!
![](/Standards/SoftwareDevelopment/RulesToBetterSharePoint/PublishingImages/ContentEditorWebPart02_Small.jpg)Figure: Content Editor Web Part looking mostly harmless...   
 So what’s bad with the Content Editor Web Part?

- The content in a content editor web part is not version controlled.
- If an editor accidentally overwrites a previous copy – there’s no way to go back.
- If an editor accidentally deletes a Content Editor Web Part – the content in it is lost.
- Data loss is always bad – and Content Editor Web Part gives you many different ways you can easily lose data... tread carefully and know the risks!


 The best practice is: 

1. Do your content editing in the Content Editor Web Part, or in SharePoint Designer?
2. Click the Source Editor button afterwards to get the RAW html view.
3. Copy and save this to a plain HTML file, and save the file in the page library (which is version controlled).
4. In the Content Editor Web Part – link to the HTML page’s URL.
<br>    a.If the text is very tiny – may be just a big heading, you may not want to do this.
<br>    b.Using Content Link is also another way you can re-use the same text in different web pages and update them in one place – very good for big banners.

![](/Standards/SoftwareDevelopment/RulesToBetterSharePoint/PublishingImages/ContentEditorWebPart03_Small.jpg) Figure: Using Content Link to a file - safely stored in the document library. This gives us the best of both worlds 
