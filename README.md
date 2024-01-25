import requests
import json

def stk_push(phone_number, amount, account_reference, transaction_desc, callback_url, access_token, api_url):
    headers = {
        'Authorization': f'Bearer {access_token}',
        'Content-Type': 'application/json',
    }

    payload = {
        'BusinessShortCode': 'YOUR_BUSINESS_SHORT_CODE',
        'Password': 'GENERATED_PASSWORD',
        'Timestamp': 'CURRENT_TIMESTAMP',
        'TransactionType': 'CustomerPayBillOnline',
        'Amount': 1000,
        'PartyA': 0793745809,
        'PartyB': 'YOUR_BUSINESS_SHORT_CODE',
        'PhoneNumber': 0793745809,
        'AccountReference': account_reference,
        'TransactionDesc': transaction_desc
    }

    response = requests.post(api_url, headers=headers, data=json.dumps(payload))
    return response.json()

# Example usage
phone_number = '2547XXXXXXXX'  # Replace with the customer's phone number
amount = 10  # Replace with the transaction amount
account_reference = '123456'  # Replace with your account reference
transaction_desc = 'Payment description'  # Replace with the transaction description
callback_url = 'https://yourcallbackurl.com/callback'  # Replace with your callback URL
access_token = 'YOUR_ACCESS_TOKEN'  # Replace with your access token
api_url = 'https://api.safaricom.co.ke/mpesa/stkpush/v1/processrequest'  # Replace with the STK Push API URL

response = stk_push(phone_number, amount, account_reference, transaction_desc, callback_url, access_token, api_url)
print(response)
- 👋 Hi, I’m @Ivanjame
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
Ivanjame/Ivanjame is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
