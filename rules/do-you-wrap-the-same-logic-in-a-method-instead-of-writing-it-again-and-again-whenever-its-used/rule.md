---
type: rule
title: Do you wrap the same logic in a method instead of writing it again and again whenever it's used?
uri: do-you-wrap-the-same-logic-in-a-method-instead-of-writing-it-again-and-again-whenever-its-used
created: 2018-04-26T23:35:54.0000000Z
authors:
- id: 1
  title: Adam Cogan

---

 
Is your code DRY? ​​If a logic (a piece of code) will occur more than once, please make it a method and call it whenever it's used. This will reduce redundancy, decrease maintenance effort, improve efficiency and reusability, and make the code more clear to read.​​​​
 
public class WarningEmail
{
//...
public void SendWarningEmail(string pFrom, string pTo, string pCC, string pUser, string pPwd, string pDomain)
{
//...
MailMessage sMessage = new MailMessage();
sMessage.From = new MailAddress(pFrom);
sMessage.To.Add(pTo);
sMessage.CC.Add(pCC);
sMessage.Subject = "This is a Warning";
sMessage.Body = GetWarning();
SmtpClient sSmtpClient = new SmtpClient();
sSmtpClient.Credentials = new NetworkCredential(pUser, pPwd, pDomain);
sSmtpClient.Send(sMessage);
//...
}
}
public class ErrorEmail
{
public void SendErrorEmail(string pFrom, string pTo, string pCC, string pUser, string pPwd, string pDomain)
{
//...
MailMessage sMessage = new MailMessage();
sMessage.From = new MailAddress(pFrom);
sMessage.To.Add(pTo);
sMessage.CC.Add(pCC);
sMessage.Subject = "This is a Error";
sMessage.Body = GetError();
SmtpClient sSmtpClient = new SmtpClient();
sSmtpClient.Credentials = new NetworkCredential(pUser, pPwd, pDomain);
sSmtpClient.Send(sMessage);
//...
}
}
Bad Example: Write the same logic repeatedly 



public class WarningEmail
{
//...
public void SendWarningEmail(string pFrom, string pTo, string pCC, string pUser, string pPwd, string pDomain)
{
//...
EmailHelper.SendEmail(pFrom, pTo, pCC, "This is a Warning", GetWarning(), pUser, pPwd, pDomain);
//...
}
}
public class ErrorEmail
{
public void SendErrorEmail(string pFrom, string pTo, string pCC, string pUser, string pPwd, string pDomain)
{
//...
EmailHelper.SendEmail(pFrom, pTo, pCC, "This is an Error", GetError(), pUser, pPwd, pDomain);
//...
}
}
public class EmailHelper
{ 
public static void SendEmail(string pFrom, string pTo, string pCC, string pSubject, string pBody, string pUser, string pPwd, string pDomain)
{
MailMessage sMessage = new MailMessage();
sMessage.From = new MailAddress(pFrom);
sMessage.To.Add(pTo);
sMessage.CC.Add(pCC);
sMessage.Subject = pSubject;
sMessage.Body = pBody;
SmtpClient sSmtpClient = new SmtpClient();
sSmtpClient.Credentials = new NetworkCredential(pUser, pPwd, pDomain);
sSmtpClient.Send(sMessage);
} 
}
Good Example: Put the same logic in a method and make it reusable​ 

