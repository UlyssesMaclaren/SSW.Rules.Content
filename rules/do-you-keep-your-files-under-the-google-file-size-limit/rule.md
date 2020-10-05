---
type: rule
title: Do you keep your files under the Google file size limit?
uri: do-you-keep-your-files-under-the-google-file-size-limit
created: 2015-11-10T19:57:28.0000000Z
authors:
- id: 1
  title: Adam Cogan

---

​As per Google  [Specifications](https&#58;//support.google.com/gsa/answer/4411411#settings):

A maximum file size may be enforced per crawler. Content which is after the maximum file size may be ignored. Google currently enforces a size limit of 500kb.
 
Regarding other files:

- All files larger than 30MB will be completely ignored.
- HTML, the search appliance indexes up to 2.5MB of the document, caches it, and discards the rest.
- A non-HTML format, the search appliance:


1. Downloads the non-HTML file.
2. Converts the non-HTML file to HTML.
3. If the converted content is less than 4,000,000 bytes, indexes the first 2MB of the HTML file. (Take note that 4MB=4,194,304 bytes.) If the converted content exceeds 4,000,000 bytes, the document is not indexed. However, the document and a link to it do appear in search results.
4. Caches the first 2MB of the HTML file.
5. Discards the rest of the HTML file and the non-HTML file.​
