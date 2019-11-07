---
type: rule
title: Schema - Do you add zs prefix to system tables?
uri: schema---do-you-add-zs-prefix-to-system-tables
created: 2019-11-07T20:39:28.0000000Z
authors:
- id: 1
  title: Adam Cogan

---



<span class='intro'> <p class="ssw15-rteElement-P">Any type of table in a database where that does not contain application data should be called zs. So when the other application (e.g. SSW SQL Deploy) or the programmer populates the table then it should be called zs (e.g. zsDate - the program populates it, zsVersion - the programmer populates it).​​<br></p> </span>




