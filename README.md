import 'dart:convert';
import 'package:http/http.dart' as http;

Future<void> sendSTKPushRequest(String accessToken, int amount, String phoneNumber) async {
  var url = Uri.parse('https://sandbox.safaricom.co.ke/mpesa/stkpush/v1/processrequest');
  var headers = {
    'Authorization': 'Bearer $accessToken',
    'Content-Type': 'application/json',
    'Accept': 'application/json',
  };
  var body = jsonEncode({
    "BusinessShortCode": 174379,
    "Password": "MTc0Mzc5YmZiMjc5ZjlhYTliZGJjZjE1OGU5N2RkNzFhNDY3Y2QyZTBjODkzMDU5YjEwZjc4ZTZiNzJhZGExZWQyYzkxOTIwMjEwOTAxMTEwNTI4",
    "Timestamp": "20240125110528",
    "TransactionType": "CustomerPayBillOnline",
    "Amount": 1000,
    "PartyA": 0793745809,
    "PartyB": 174379,
    "PhoneNumber": 0793745809,
    "CallBackURL": "https://mydomain.com/path",
    "AccountReference": "CHATMATE",
    "TransactionDesc": "Payment of X"
  });

  try {
    var response = await http.post(url, headers: headers, body: body);
    if (response.statusCode == 200) {
      // Handle the response here
      print('Transaction successful');
    } else {
      // Handle the error
      print('Error: ${response.statusCode}');
    }
  } catch (e) {
    // Handle any errors that occur during the HTTP request
    print('Error: $e');
  }
}
