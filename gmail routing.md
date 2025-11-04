Gmail Email Routing Setup
Step 1: Cloudflare Email Routing (Receiving)

In Cloudflare Dashboard → Click "Email" in left sidebar
Enable Email Routing → Click "Get started"
Add your personal Gmail as destination email
Verify your email (check inbox for Cloudflare verification link)
Create email addresses:

hello@velocitydev.ai → forwards to your Gmail
ventures@velocitydev.ai → forwards to your Gmail



Step 2: Gmail Send Setup (Sending FROM custom email)

Open Gmail (desktop) → Settings ⚙️ → "See all settings"
"Accounts and Import" tab
Under "Send mail as" → Click "Add another email address"
Enter details:

Name: Your Name or "VelocityDev"
Email: hello@velocitydev.ai
☑️ Check "Treat as an alias"


SMTP Settings:

SMTP Server: smtp.gmail.com
Port: 587
Username: Your Gmail address
Password: Your Gmail password (or App Password*)
☑️ TLS selected


Verify by clicking the link in the confirmation email
Repeat for ventures@velocitydev.ai

Gmail App Password (if needed):

Go to: https://myaccount.google.com/apppasswords
Generate app password for "Mail"
Use this instead of your regular Gmail password

Now you can receive emails at your custom addresses (they forward to Gmail) and send FROM those addresses in Gmail!