# EBulkSMS Python Library
The EBulkSMS Python library provides a simple interface for sending SMS messages using the eBulkSMS API. It allows you to send SMS messages to multiple recipients, check your account balance, retrieve delivery reports, and more.

## Prerequisites
Before using the EBulkSMS library, make sure you have the following:
- An active account with (EbulkSMS)[https://www.ebulksms.com/signup].
- An API token or login credentials (email and password) associated with your eBulkSMS account.

## Installation
To use the EBulkSMS library, you need to install the requests library. You can install it using pip:

pip install requests

## Getting Started
To begin using the EBulkSMS library, import it into your Python script:

### Initializing the EBulkSMS Object
The EBulkSMS class provides the necessary methods for interacting with the eBulkSMS API. To get started, create an instance of the EBulkSMS class:

```
ebulksms = EBulkSMS(api_token=None, email=None, password=None)
```

You can initialize the EBulkSMS object in two ways:
- Using an API token:
```
ebulksms = EBulkSMS(api_token="your_api_token", email="your_email@example.com")
```

- Using email and password:
```
ebulksms = EBulkSMS(email="your_email@example.com", password="your_password")
```
Note: Provide either an API token or email and password arguments.

### Sending SMS Messages
To send an SMS message, use the sendSMS method:

```
sender = "YourSenderName"
recipients = ["234XXXXXXXXX", "234YYYYYYYYY"]
message = "Your message goes here"

response = ebulksms.sendSMS(sender, recipients, message)
print(response)
```
The sendSMS method takes the following parameters:

`sender`: The name or number that will appear as the sender of the message.
`recipients`: A list of phone numbers (in international format) to which the message will be sent.
`message`: The content of the SMS message.

The method returns a JSON response containing information about the sent message.

### Checking Account Balance
To retrieve your account balance, use the getBalance method:

```
balance = ebulksms.getBalance()
print(balance)
```

The getBalance method returns the account balance as a floating-point number.

### Retrieving Delivery Reports
To get the delivery report for a specific message, use the getDeliveryReport method:

```
unique_id = "your_message_unique_id"
report = ebulksms.getDeliveryReport(unique_id)
print(report)
```

The getDeliveryReport method takes the unique_id of the message as a parameter and returns the delivery report in JSON format.

Note: The `unique_id` is generated automatically when sending the SMS message.

## Error Handling
The EBulkSMS library raises ValueError exceptions when encountering errors. Make sure to handle these exceptions appropriately in your code.

## Contributing
We welcome contributions from the community! If you would like to contribute to the EBulkSMS Python library, please follow these guidelines:

1. Fork the repository and create your branch from the `main` branch.
2. Make your changes and ensure that the code passes all tests.
3. Write clear and concise commit messages.
4. Submit a pull request to the `main` branch.

### Code Style
Please adhere to the following code style guidelines:
- Use PEP 8 style guide for Python code.
- Write clear and meaningful variable and function names.
- Include comments to explain complex logic or important details.
- Follow the existing code formatting and structure.

### Bug Reports and Feature Requests
If you encounter any bugs or have suggestions for new features, please open an issue on the GitHub repository. Provide a clear description of the problem or feature request and any relevant details.

### Contact
If you have any questions or need assistance, you can reach out to us

We appreciate your contributions and thank you for helping improve the EBulkSMS Python library!