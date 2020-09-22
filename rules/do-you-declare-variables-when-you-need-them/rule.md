---
type: rule
title: Do you declare variables when you need them?
uri: do-you-declare-variables-when-you-need-them
created: 2018-04-24T21:55:53.0000000Z
authors:
- id: 1
  title: Adam Cogan

---

 
Should you declare variables at the top of the function, or declare them when you need to use them? If you come back to your code after a few weeks and you no longer need a variable, you are quite likely to forget to delete the declaration at the top, leaving orphaned variables. Here at SSW, we believe that variables should be declared as they are needed.​
 
​Private Sub Command0\_Click()
Dim dteTodayDate As Date
Dim intRoutesPerDay As Integer
Dim intRoutesToday As Integer
Dim dblWorkLoadToday As Double
dblWorkLoadToday = Date.Now()
.
....many lines of code...
.
intRoutesPerDay = 2
End Sub
  Figure: Bad example 



Private Sub Command0\_Click()
Dim dteTodayDate As Date
dteTodayDate = Date.Now()
.
....many lines of code...
.
Dim intRoutesPerDay As Integer
intRoutesPerDay = 2
.
....continuing code...
.End Sub
​Figure: Good example​​

