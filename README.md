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


# Receivers
There are two ways to send multiple emails:

1) Create a spreadsheet, i.e. *emails-list.xlsx*, with two columns like the image below:

![image](https://user-images.githubusercontent.com/56649205/76107127-e80bde80-5fb6-11ea-9260-16e4ffd44a09.png)

Then extract the emails from Excel to a list using the code:
```Python
#--------- DESTINATION -------------------
# Get Email's list with Excel Workbook
wb = load_workbook("emails-list.xlsx")  # Work Book
ws = wb['Plan1']  # Work Sheet
column = ws['B']  # Column
emails = [column[x].value for x in range(len(column))] # list with all e-mails
print('LISTA DE DESTINATÁRIOS: ')
print(emails)
print('\nTotal de emails a ser enviados: ' + str(len(emails)))
```
After that, all destinations will be in *emails* list. I prefer to use this way to code *yagmail.py*. 

2) Create manually the *emails* list, like:
```Python
# Other Way - TO-list
emails=['bla1234@emailbla.com.br', 'blabla@email.com.br']
```
