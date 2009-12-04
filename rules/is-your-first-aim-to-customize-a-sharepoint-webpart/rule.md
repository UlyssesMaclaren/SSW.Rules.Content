---
type: rule
title: Is your first aim to customize a SharePoint webpart?
uri: is-your-first-aim-to-customize-a-sharepoint-webpart
created: 2009-02-28T09:14:44.0000000Z
authors:
- id: 1
  title: Adam Cogan
- id: 8
  title: John Liu

---

 This field should not be null (Remove me when you edit this field). 
These are some of the fields in the CQWP that are often configured:

**MainXslLink, ItemXslLink:**

These two controls the main and item XSL file paths.  Set these to your new XSL file under /Style Library/XSL Style Sheets/SSW/SSWMainContent.xsl and SSWItem.xsl files

**ItemLimit **

The default number of items that are displayed on a Content Query web part is 15.  With unlimited pages.  Sometimes you want this number to be a lot higher (or -1 for no limit).

Note: If you do make this unlimited - make sure your page is designed to grow infinitely or the layout may look strange.

**CommonViewFields **

The Content Query web part automatically selects a few of the common fields for any query.  But sometimes you want a particular field that isn't selected by default.  This is when you should use CommonViewFields.

The syntax is "fieldname,fieldtype;"

E.g. PublishingContent,PublishingHTML;

**Query and QueryOverride **

The Content Query web part gives the user a lot of flexibility to design the query in the UI toolpart.  However if your needs are perculiar you can use the QueryOverride to skip over defining the query and use your supplied CAML directly.




```
[Guid("5bbdb385-5076-4a4b-85e8-691664b7f575")] public class WebPart1 : System.Web.UI.WebControls.WebParts.WebPart{    public WebPart1() { }    protected override void CreateChildControls()    {        base.CreateChildControls();        // TODO: add custom rendering code here.        Label label = new Label();        label.Text = "Hello World";        this.Controls.Add(label);    }}
```

Bad Example: Inherit from System.Web.UI.WebControls.WebParts.WebPart





```
public class RelatedContentByQueryWebPart:CustomContentByQueryWebPart{    public string RulesKeyWords //get the column name from SharePoint    {        get;        set;    }    protected override void OverrideQuery()    {        StringBuilder query = new StringBuilder();        SPListItem item = SPContext.Current.ListItem;        string[] rulesKeyWords = {};        if (item != null)        {            ......        }        this.QueryOverride = query.ToString(); // pass the query    }}
```

Good Example: Inherit from CustomContentByQueryWebPart


