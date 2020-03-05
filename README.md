# EasySendMassEmail
Easy way to send multiple emails, individually targeted, to as many receivers as possible to the email server

# Requirements
* [Yagmail](https://pypi.org/project/yagmail/)

# SMTP Servers
The easiest way to connect to a SMTP Server with yagmail is using the Google Mail (Gmail) as shown below:
```Python
# ONLY GMAIL
yag = yagmail.SMTP('GMAIL-LOGIN', 'GMAIL-PASSWORD')
```
If you want to connect to other SMTP server (like outlook) just code:
```Python
# OTHER SMTP Server
yag = yagmail.SMTP('HOTMAIL LOGIN', 'HOTMAIL PASSWORD', host='smtp-mail.outlook.com', port=587, smtp_starttls=True, smtp_ssl=False)
```
Port 587 is a common port for most of SMTP servers, however some may have different ports (like 465). 

This table from [Automate Boring Stuff with Python](http://automatetheboringstuff.com/2e/chapter18/) summarizes the majority of servers:

| Provider                | SMTP server domain name      |
|-------------------------|------------------------------|
| Gmail                   | smtp.gmail.com               |
| Outlook.com/Hotmail.com | smtp-mail.outlook.com        |
| Yahoo Mail              | smtp.mail.yahoo.com          |
| AT&T                    | smpt.mail.att.net (port 465) |
| Comcast                 | smtp.comcast.net             |
| Verizon                 | smtp.verizon.net (port 465)  |
