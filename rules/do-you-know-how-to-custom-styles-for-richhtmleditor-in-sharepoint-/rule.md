

---
authors:
  - id: 9
    title: William Yin
  - id: 34
    title: Brendan Richards
---




<span class='intro'> <div><p style="margin-bottom&#58;0px;line-height&#58;20px;">​​​​​​As a CMS system, it's obviously necessary to apply standard styles to all content, so the whole site looks consistent.</p><p style="margin-bottom&#58;0px;line-height&#58;20px;"><br></p><p style="margin-bottom&#58;0px;line-height&#58;20px;">This rule outlines how to use custom styles in the SharePoint &#160;RichHTMLEditor​.<br></p><p style="margin-bottom&#58;0px;line-height&#58;20px;"><br></p><p style="margin-bottom&#58;0px;line-height&#58;20px;">In SharePoint, we can use the below way to apply custom styles&#58;</p><dl class="ssw15-rteElement-ImageArea"><img src="/PublishingImages/CustomStylesInSharePoint.png" alt="CustomStylesInSharePoint.png" style="margin&#58;5px;" /></dl><dd class="ssw15-rteElement-FigureNormal">Figure&#58; custom RichHtmlEditor styles give your content editors a visual preview of your custom styles​<br></dd><p class="separator" style="margin-bottom&#58;0px;line-height&#58;20px;clear&#58;both;"><br></p></div> </span>

<p style="margin-bottom&#58;0px;">​To do this&#58;</p><p style="margin-bottom&#58;0px;">1. You can use &quot;<strong>PrefixStyleSheet</strong>&quot; property to apply the custom styles to a build-in&#160;<strong>RichHtmlField&#160;</strong>in page layout or master page. In my case, I applied them to a custom control &quot;<strong>ParsedRichHtmlField</strong>&quot; which inherited from the system build-in one.</p><p style="margin-bottom&#58;0px;"><br></p><p style="margin-bottom&#58;0px;">&lt;SSW&#58;ParsedRichHtmlField&#160;<strong>PrefixStyleSheet=&quot;ssw15-rte&quot;</strong>&#160;CssClass=&quot;ssw-inputeditorfield&quot; id=&quot;Content&quot; FieldName=&quot;PublishingPageContent&quot; InputFieldLabel=&quot;Rule Summary Info&quot; runat=&quot;server&quot;/&gt;</p><p style="margin-bottom&#58;0px;"><br></p><p style="margin-bottom&#58;0px;">2. Refer an additional css file in the page layout or master page (apply to display mode content).</p><p style="margin-bottom&#58;0px;">&#160;&#160; &lt;SharePointWebControls&#58;CssRegistration ID=&quot;CssRegistration3&quot; &#160; Name=&quot;<strong>Themable/ssw.core.styles.v15.css</strong>&quot; runat=&quot;server&quot; &#160;EnableCssTheming=&quot;True&quot;</p><p style="margin-bottom&#58;0px;">&#160; &#160; &#160;&#160;/&gt;</p><p style="margin-bottom&#58;0px;"><br></p><p style="margin-bottom&#58;0px;">3. Refer the additional css file again in &quot;<strong>edit mode</strong>&quot; in the page layout or master page (apply to edit mode editor).</p><p style="margin-bottom&#58;0px;"><font class="Apple-tab-span" style="white-space&#58;pre;"> </font>&lt;PublishingWebControls&#58;EditModePanel ID=&quot;EditModePanel1&quot; runat=&quot;server&quot;&gt;</p><p style="margin-bottom&#58;0px;"><font class="Apple-tab-span" style="white-space&#58;pre;">  </font>&lt;!-- Styles for edit mode only--&gt;</p><p style="margin-bottom&#58;0px;"><font class="Apple-tab-span" style="white-space&#58;pre;">  </font>&lt;SharePointWebControls&#58;CssRegistration ID=&quot;CssRegistration2&quot; name=&quot;&lt;% $SPUrl&#58;~sitecollection/Style Library/~language/Themable/Core Styles/editmode15.css %&gt;&quot;</p><p style="margin-bottom&#58;0px;"><font class="Apple-tab-span" style="white-space&#58;pre;">   </font>&#160;After=&quot;&lt;% $SPUrl&#58;~sitecollection/Style Library/~language/Themable/Core Styles/pagelayouts15.css %&gt;&quot; runat=&quot;server&quot;/&gt;</p><p style="margin-bottom&#58;0px;">&#160; &#160; &#160; &#160; &lt;SharePointWebControls&#58;CssRegistration ID=&quot;CssRegistration3&quot; &#160; Name=&quot;<strong>Themable/ssw.core.styles.v15.css</strong>&quot; runat=&quot;server&quot; &#160;EnableCssTheming=&quot;True&quot;</p><p style="margin-bottom&#58;0px;">&#160; &#160; &#160; &#160; &#160; &#160; &#160;<strong>After</strong>=&quot;&lt;%$SPUrl&#58;~sitecollection/Style Library/~language/Themable/Core Styles/<strong>editmode15.css</strong>&#160;&#160;%&gt;&quot; /&gt;</p><p style="margin-bottom&#58;0px;"><font class="Apple-tab-span" style="white-space&#58;pre;"> </font>&lt;/PublishingWebControls&#58;EditModePanel&gt;</p><p style="margin-bottom&#58;0px;">Use &quot;<strong>After</strong>&quot; property to ensure that it will be loaded after the &quot;<strong>editmode15.css</strong>&quot;, which is SharePoint default edit mode style. The custom style css file will be applied to the ribbon after users change to edit mode.</p><p style="margin-bottom&#58;0px;"><br></p><p style="margin-bottom&#58;0px;">4. Add your custom styles definitions into the additional css file, all styles' names should start with the value you set for&#160;<strong>PrefixStyleSheet</strong>, in our case, it's &quot;<strong>ssw15-rte</strong>&quot;. The custom styles can be applied to different areas (cases) in the ribbon.</p><p style="margin-bottom&#58;0px;">1) .ssw15-rte<strong>Language -&#160;</strong>As SharePoint support multiple language, this definition will&#160;tell SharePoint which language will use those custom styles.</p><p style="margin-bottom&#58;0px;">e.g.</p><p style="margin-bottom&#58;0px;">.ssw15-rteLanguage-en &#123;</p><p style="margin-bottom&#58;0px;">&#160; &#160; -ms-name&#58; English;</p><p style="margin-bottom&#58;0px;">&#125;</p><p style="margin-bottom&#58;0px;">2) .ssw15-rte<strong>Element&#160;-&#160;</strong>tell SharePoint which element will be applied with this style. When you press &quot;Enter&quot; in SharePoint editor, it will automatically start a new paragraph with &quot;&lt;P&gt;&lt;/P&gt;&quot;, so it's a brilliant choice to make some custom &quot;paragraph&quot; elements.</p><p style="margin-bottom&#58;0px;">e.g.</p><p style="margin-bottom&#58;0px;">P.ssw15-rteElement-CodeArea</p><p style="margin-bottom&#58;0px;">&#123;<font class="Apple-tab-span" style="white-space&#58;pre;"> </font></p><p style="margin-bottom&#58;0px;"><font class="Apple-tab-span" style="white-space&#58;pre;"> </font><strong>-ms-name&#58;&quot;Code Area&quot;;</strong></p><p style="margin-bottom&#58;0px;"><font class="Apple-tab-span" style="white-space&#58;pre;"> </font>border&#58; solid #CCC;</p><p style="margin-bottom&#58;0px;"><font class="Apple-tab-span" style="white-space&#58;pre;"> </font>border-width&#58; 1px 1px 1px 10px;</p><p style="margin-bottom&#58;0px;"><font class="Apple-tab-span" style="white-space&#58;pre;"> </font>background&#58; #EEE;</p><p style="margin-bottom&#58;0px;"><font class="Apple-tab-span" style="white-space&#58;pre;"> </font>padding&#58; 5px 10px;</p><p style="margin-bottom&#58;0px;"><font class="Apple-tab-span" style="white-space&#58;pre;"> </font>margin&#58; 8px;</p><p style="margin-bottom&#58;0px;"><font class="Apple-tab-span" style="white-space&#58;pre;"> </font>overflow-x&#58;auto;</p><p style="margin-bottom&#58;0px;"><font class="Apple-tab-span" style="white-space&#58;pre;"> </font>display&#58;block;</p><p style="margin-bottom&#58;0px;"><font class="Apple-tab-span" style="white-space&#58;pre;"> </font>width&#58;93%;</p><p style="margin-bottom&#58;0px;"><font class="Apple-tab-span" style="white-space&#58;pre;"> </font>font-size&#58;12px;</p><p style="margin-bottom&#58;0px;">&#125;</p><p style="margin-bottom&#58;0px;">This&#160;<strong>Code Area</strong>&#160;style will come up in &quot;Page Elements&quot; section&#58;​</p><dl class="ssw15-rteElement-ImageArea"><img src="/PublishingImages/CodeArea.png" alt="CodeArea.png" style="margin&#58;5px;" /></dl><dd class="ssw15-rteElement-FigureNormal">Figure&#58; Code Area style come up in &quot;Page Elements&quot; seciton</dd><p class="separator" style="margin-bottom&#58;0px;clear&#58;both;"><br></p><p class="separator" style="margin-bottom&#58;0px;clear&#58;both;">While applying a &quot;Page Elements&quot; style, it will</p><p style="margin-bottom&#58;0px;"><br></p><ul><li>Remove all the styles for the children elements</li><li>It may change both the class name and the parent element type, it depends on which html element has been specified in the definition.</li></ul><div><p style="margin-bottom&#58;0px;">For example, we change the style&#160;</p></div><div><p style="margin-bottom&#58;0px;">from&#160;</p><div><p style="margin-bottom&#58;0px;"><strong>P</strong>.ssw15-rteElement-CodeArea</p></div><div><p style="margin-bottom&#58;0px;">to</p></div><div><p style="margin-bottom&#58;0px;"><strong>dd</strong>.ssw15-rteElement-FigureGood</p></div><div><p style="margin-bottom&#58;0px;"><br></p></div><div><p style="margin-bottom&#58;0px;">Its html code will change&#160;</p></div><div><p style="margin-bottom&#58;0px;">from</p><dl class="ssw15-rteElement-ImageArea"><img src="/PublishingImages/page_element_p.png" alt="page_element_p.png" style="margin&#58;5px;width&#58;650px;" /></dl></div><div><dd class="ssw15-rteElement-FigureNormal">Figure&#58; &quot;Code Area style&quot; with parent element &lt;p&gt;</dd></div><div><p style="margin-bottom&#58;0px;">to</p><dl class="ssw15-rteElement-ImageArea"><img src="/PublishingImages/page_element_dd.png" alt="page_element_dd.png" style="margin&#58;5px;width&#58;650px;" /></dl><dl class="ssw15-rteElement-ImageArea"><span style="color&#58;#555555;font-size&#58;11px;font-weight&#58;bold;">Figure&#58; &quot;Good Figure style&quot;&#160;changed the&#160;parent element from &lt;p&gt; to&#160;&lt;dd&gt;</span><br></dl><dl class="ssw15-rteElement-ImageArea"><br></dl></div><div><p style="margin-bottom&#58;0px;color&#58;#000000;font-family&#58;'times new roman';font-size&#58;medium;line-height&#58;normal;">3).ssw15-rte<strong>Style&#160;-&#160;</strong>this style could be applied to&#160;<strong>Text Styles</strong>&#58;</p><p style="margin-bottom&#58;0px;color&#58;#000000;font-family&#58;'times new roman';font-size&#58;medium;line-height&#58;normal;"><br></p><p style="margin-bottom&#58;0px;color&#58;#000000;font-family&#58;'times new roman';font-size&#58;medium;line-height&#58;normal;">e.g.</p><p style="margin-bottom&#58;0px;color&#58;#000000;font-family&#58;'times new roman';font-size&#58;medium;line-height&#58;normal;">.ssw15-rteStyle-Highlight</p><p style="margin-bottom&#58;0px;color&#58;#000000;font-family&#58;'times new roman';font-size&#58;medium;line-height&#58;normal;">&#123;</p><p style="margin-bottom&#58;0px;color&#58;#000000;font-family&#58;'times new roman';font-size&#58;medium;line-height&#58;normal;"><font class="Apple-tab-span" style="white-space&#58;pre;"> </font><strong>-ms-name&#58;&quot;Highlight&quot;;</strong></p><p style="margin-bottom&#58;0px;color&#58;#000000;font-family&#58;'times new roman';font-size&#58;medium;line-height&#58;normal;"><font class="Apple-tab-span" style="white-space&#58;pre;"> </font>background-color&#58; #FFFF00;</p><p style="margin-bottom&#58;0px;color&#58;#000000;font-family&#58;'times new roman';font-size&#58;medium;line-height&#58;normal;">&#125;</p><p style="margin-bottom&#58;0px;color&#58;#000000;font-family&#58;'times new roman';font-size&#58;medium;line-height&#58;normal;">This&#160;<strong>Highlight</strong>&#160;style will come up in &quot;Text Styles&quot; section&#58;​</p><dl class="ssw15-rteElement-ImageArea"><img src="/PublishingImages/HighLight.png" alt="HighLight.png" style="margin&#58;5px;" /></dl><dd class="ssw15-rteElement-FigureNormal">Figure&#58;&#160;Highlight&#160;style will come up in &quot;Text Styles&quot; section​<br></dd><dl class="ssw15-rteElement-ImageArea"><br></dl><p style="margin-bottom&#58;0px;color&#58;#000000;font-family&#58;'times new roman';font-size&#58;medium;line-height&#58;normal;">While applying a&#160;&quot;Text Styles&quot;&#160;style, it will</p><p style="margin-bottom&#58;0px;color&#58;#000000;font-family&#58;'times new roman';font-size&#58;medium;line-height&#58;normal;"><br></p><ul style="color&#58;#000000;font-family&#58;'times new roman';font-size&#58;medium;line-height&#58;normal;"><li>nest the text in a &lt;span&gt; tag with the style class if the text is not already inside an HTML tag</li><li>replace the class of the HTML tag if this tag is a &lt;span&gt; tag</li></ul><p style="margin-bottom&#58;0px;color&#58;#000000;font-family&#58;'times new roman';font-size&#58;medium;line-height&#58;normal;"><br></p><p style="margin-bottom&#58;0px;color&#58;#000000;font-family&#58;'times new roman';font-size&#58;medium;line-height&#58;normal;">That means all &quot;Text Styles&quot; will apply to &lt;span&gt; tag, and you cannot apply two &quot;Text Styles&quot; to one &lt;span&gt; (e.g. apply both Strike and Hightlight), you may have to do that via changing html source code&#160;manually, or creating a &quot;combined&quot; &quot;Text Styles&quot;.</p><p style="margin-bottom&#58;0px;color&#58;#000000;font-family&#58;'times new roman';font-size&#58;medium;line-height&#58;normal;"><br></p><p style="margin-bottom&#58;0px;color&#58;#000000;font-family&#58;'times new roman';font-size&#58;medium;line-height&#58;normal;">4) .ssw15-rte<strong>Table -</strong>&#160;Tell SharePoint the definition of custom table styles. After inserting a table, you can see the styles under &quot;Design&quot; tab&#58;​</p><p style="margin-bottom&#58;0px;color&#58;#000000;font-family&#58;'times new roman';font-size&#58;medium;line-height&#58;normal;">​<br></p><p style="margin-bottom&#58;0px;color&#58;#000000;font-family&#58;'times new roman';font-size&#58;medium;line-height&#58;normal;"><br></p><p style="margin-bottom&#58;0px;color&#58;#000000;font-family&#58;'times new roman';font-size&#58;medium;line-height&#58;normal;">e.g. The below is a &quot;<strong>SSW Table</strong>&quot; style definition&#58;</p><p style="margin-bottom&#58;0px;color&#58;#000000;font-family&#58;'times new roman';font-size&#58;medium;line-height&#58;normal;">.ssw15-rte<strong>Table-</strong>default</p><p style="margin-bottom&#58;0px;color&#58;#000000;font-family&#58;'times new roman';font-size&#58;medium;line-height&#58;normal;">&#123;</p><p style="margin-bottom&#58;0px;color&#58;#000000;font-family&#58;'times new roman';font-size&#58;medium;line-height&#58;normal;"><font class="Apple-tab-span" style="white-space&#58;pre;"> </font><strong>-ms-name&#58;&quot;SSW Table&quot;;</strong></p><p style="margin-bottom&#58;0px;color&#58;#000000;font-family&#58;'times new roman';font-size&#58;medium;line-height&#58;normal;"><font class="Apple-tab-span" style="white-space&#58;pre;"> </font>border&#58;1px solid #ddd;</p><p style="margin-bottom&#58;0px;color&#58;#000000;font-family&#58;'times new roman';font-size&#58;medium;line-height&#58;normal;"><font class="Apple-tab-span" style="white-space&#58;pre;"> </font>margin&#58; 8px;</p><p style="margin-bottom&#58;0px;color&#58;#000000;font-family&#58;'times new roman';font-size&#58;medium;line-height&#58;normal;"><font class="Apple-tab-span" style="white-space&#58;pre;"> </font>width&#58;98%;</p><p style="margin-bottom&#58;0px;color&#58;#000000;font-family&#58;'times new roman';font-size&#58;medium;line-height&#58;normal;"><font class="Apple-tab-span" style="white-space&#58;pre;"> </font>background-color&#58;#f0f0f0;</p><p style="margin-bottom&#58;0px;color&#58;#000000;font-family&#58;'times new roman';font-size&#58;medium;line-height&#58;normal;">&#125;</p><p style="margin-bottom&#58;0px;color&#58;#000000;font-family&#58;'times new roman';font-size&#58;medium;line-height&#58;normal;"><br></p><p style="margin-bottom&#58;0px;color&#58;#000000;font-family&#58;'times new roman';font-size&#58;medium;line-height&#58;normal;">After finishing the definitions of custom styles, make a package and deploy to a SharePoint site, Create a page using the page layout or master page which you added custom RichHtmlField style, then you should be able to see the custom styles in the ribbon.</p><p style="margin-bottom&#58;0px;color&#58;#000000;font-family&#58;'times new roman';font-size&#58;medium;line-height&#58;normal;"><br></p><p style="margin-bottom&#58;0px;color&#58;#000000;font-family&#58;'times new roman';font-size&#58;medium;line-height&#58;normal;">Enjoy!</p></div></div><div><br></div>

