# Gmail birthday wish sender

1. Enter your gmail in script
2. Enter your password in script
3. Enter the email id of person you want to send
4. Enter your birthday wishes

## smtp

- simple mail transfer protocol
  - about sending process
- smtp server
  - handles the message transfer
- smtp port
- process
  - client connection to SMTP server
    - Firstly, needs SMTP server to establish
    - then once user hits 'send', SMTP connection will open
  - transfer data
    - SMTP client uses commands to tell what to do

## smtplib

## MIME

- an extension for SMTP that allows non-ASCII data to be sent

### how to send mail

Because of google [blocks low secure apps login to gmail](https://github.com/kootenpv/yagmail?tab=readme-ov-file), it becomes hard to send mail via gmail server using python.
So I will use yagmail.

1. create google account if you don't have it
2. Turn on [2-Step Verification](https://support.google.com/accounts/answer/185839)
   - see more details at [this article](https://support.google.com/accounts/answer/185833)
3. Create [an application password](https://support.google.com/accounts/answer/185833#zippy=%2Cremove-app-passwords)
4. Enter your gmail account, an application password in the script
