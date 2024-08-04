Door Code Sender Bot
This bot automates the process of sending door codes to hotel guests via Telegram. It retrieves emails from the hotel's ERP system containing door codes and phone numbers of guests, then sends the door codes to the guests' phone numbers using Telegram.

Value
Automation: Saves time and reduces errors by automating the process of sending door codes to guests.
Efficiency: Ensures timely delivery of door codes, improving the guest experience.
Integration: Seamlessly integrates with the hotel's existing ERP system and email infrastructure.
Scalability: Can handle any number of bookings and emails, making it suitable for hotels of all sizes.
Instructions for Use


1. 
Clone the Repository

git clone https://github.com/yourusername/door-code-sender-bot.git
cd door-code-sender-bot

2.
Install Dependencies
Ensure you have Python installed. Then, install the required packages:

pip install -r requirements.txt


3.
Configuration
Create a .env file in the root directory of the project and add your configuration settings:

IMAP_SERVER=imap.example.com
IMAP_USER=hotel@example.com
IMAP_PASS=your-email-password
TELEGRAM_TOKEN=your-telegram-bot-token

4.
Run the Bot

python bot.py


5.
Customize (Optional)

If your email format or structure differs, you may need to adjust the email parsing logic in bot.py to correctly extract the door code and phone number.

Detailed Explanation
Booking and ERP Integration

When a guest books a room via Booking, their phone number is sent to the hotel's ERP system.
The ERP system generates a door code for the guest and sends it in an email to the hotel's designated email address.
Email Retrieval

The bot connects to the hotel's email inbox using the IMAP protocol.
It searches for emails from the ERP system containing door codes.
Email Parsing

The bot fetches the latest email from the ERP system.
It parses the email to extract the door code and the guest's phone number.
Sending Door Code via Telegram

The bot formats the phone number if necessary (ensuring it includes the country code).
It sends the extracted door code to the guest's phone number using the Telegram Bot API.
Example
Here’s an example configuration for the .env file:


IMAP_SERVER=imap.gmail.com
IMAP_USER=hotelbooking@example.com
IMAP_PASS=mysecurepassword
TELEGRAM_TOKEN=123456789:ABCdefGhijKlmNoPQrstUVwxyz1234567890


Run the bot with:

python bot.py

This will start the bot, which will periodically check for new emails from the ERP system and send the door codes to guests via Telegram.

