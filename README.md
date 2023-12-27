# Email-Sending-with-SMTP
 Send an email using the smtplib library in Python.
import smtplib
from email.mime.text import MIMEText

sender_email = 'your_email@gmail.com'
receiver_email = 'recipient_email@gmail.com'
subject = 'Subject of the email'
body = 'Body of the email'

message = MIMEText(body)
message['Subject'] = subject
message['From'] = sender_email
message['To'] = receiver_email

with smtplib.SMTP('smtp.gmail.com', 587) as server:
    server.starttls()
    server.login(sender_email, 'your_email_password')
    server.sendmail(sender_email, [receiver_email], message.as_string())
