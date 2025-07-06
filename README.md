# google-form-email-automation
Automated hotel payment email confirmation using Google Forms, Sheets &amp; Apps Script.

📬 Google Form Email Automation for Hotel Payment Confirmation

🧠 Project Overview
I built an automation system using Google Forms, Google Sheets, and Google Apps Script that automatically sends a confirmation email to the hotel owner whenever a customer submits a payment form.

📌 Problem
The hotel’s manual workflow for tracking guest payments was time-consuming and prone to delays. Staff had to:

• Constantly monitor form responses in Google Sheets
• Manually draft and send payment confirmation emails
• Risk missing entries or sending late responses, which could affect customer satisfaction and internal coordination

🚀 Solution
Using Google Apps Script, I automated the process to:
• Read form responses instantly
• Format the message
• Send an email with all details to the hotel owner automatically

🛠️ Tools Used
• Google Forms
• Google Sheets
• Google Apps Script (JavaScript-based)
• MailApp Service (built-in Google service)

💻 Code
// Function that sends an email when form is submitted
function sendEmail(e) {
  var name = e.values[1];
  var contact = e.values[2];
  var room = e.values[3];
  var checkin = e.values[4];
  var checkout = e.values[5];
  var amount = e.values[6];
  var paymentMethod = e.values[7];

  var message = "New hotel payment confirmed:\n\n" +
                "Name: " + name + "\n" +
                "Contact number: " + contact + "\n" +
                "Room number: " + room + "\n" +
                "Check-in date: " + checkin + "\n" +
                "Check-out date: " + checkout + "\n" +
                "Amount: " + amount + "\n" +
                "Payment Method: " + paymentMethod;

  MailApp.sendEmail("alvinzipagan09@gmail.com", "New Payment Confirmation", message);
}

// Trigger setup (run this once)
function setupTrigger() {
  var ss = SpreadsheetApp.getActive();
  ScriptApp.newTrigger("sendEmail")
    .forSpreadsheet(ss)
    .onFormSubmit()
    .create();
}

🖼️ Screenshots to Include

Screenshot                     What to Show                                                                                             IMAGE
✅ Form Screenshot            Your Google Form with sample fields: Name, Contact, Room, etc.          ![image](https://github.com/user-attachments/assets/c475480a-1787-4f09-81af-49091f8caf45)
✅ Google Sheet               The linked response spreadsheet showing the submitted answers           ![image](https://github.com/user-attachments/assets/914445c1-b8fa-4737-af24-5af756cb3789)
✅ Script Editor              The Apps Script code window with the code above pasted in               ![image](https://github.com/user-attachments/assets/87fb1925-6c55-4865-8931-0f2bcc2eb265)
✅ Email Result               A screenshot of the actual confirmation email received                  ![image](https://github.com/user-attachments/assets/698a9a5a-8deb-4a68-a6f9-51c3b7402b0f)

📋 Step-by-Step Instructions

1. Create a Google Form
• Add fields: Name, Contact, Room Number, Check-in, Check-out, Amount Paid, Payment Method

2. Link Form to Google Sheet
• Go to Responses > Click Link to Sheet

3. Open Script Editor
• In the Google Sheet > Extensions > Apps Script

4. Paste the Code
• Paste the sendEmail and setupTrigger functions

5. Run setupTrigger() Manually
• Click the play ▶️ button to allow the script to run and create the trigger
• Authorize access when prompted

6. Test the Form
• Submit a test form
• Check your Gmail inbox for the automated confirmation email

📈 Impact
• Reduced manual work
• Ensured instant notifications
• Created a scalable system for multiple bookings

💬 Talking Point

One of the projects I completed involved automating the confirmation system for hotel payments using Google Forms and Apps Script. It helped streamline operations by sending structured emails to the admin every time a customer submitted payment info. I used JavaScript in Google Apps Script to access the form data, format a message, and send an email in real-time.
