## SMSReceiver-iOS

SMSReceiver-iOS is a straightforward iOS code that enables you to forward received SMS messages to an online server. It was developed with the purpose of forwarding all bank-related SMS messages to [smartMoney](https://github.com/mrahmadt/smartMoney), which then parses the bank SMS transactions (while discarding non-bank ones) and automates the creation of transactions in [FireFly-III](https://github.com/firefly-iii/firefly-iii/).

This code relies on the iOS [SMS and MMS Message Filtering](https://developer.apple.com/documentation/sms_and_call_reporting/sms_and_mms_message_filtering/) capability to capture SMS messages and send them to the service, marking all SMS messages as non-spam. Due to iOS design limitations, this is the only way to access all SMS messages.

To use this code, you'll need to update the server URL in your Info.plist file and also update .well-known/apple-app-site-association.

Setting up the code is straightforward, but you should be familiar with Xcode. Please note that due to [iOS design restrictions](https://developer.apple.com/library/archive/documentation/General/Conceptual/ExtensibilityPG/ExtensionScenarios.html), you cannot build and publish this app because the server URL is hardcoded in the source code, making it impossible to identify the user. Typically, I connect my iPhone to Xcode, run the code in debug mode, and then disconnect my phone, allowing the app to keep running.

To get the app up and running, you'll need the following:
- An Apple Developer Program account
- A domain name with SSL (you can use [FreeDNS](https://freedns.afraid.org/) with [Let's Encrypt](https://letsencrypt.org/))
- Follow Apple's [SMS and MMS Message Filtering](https://developer.apple.com/documentation/sms_and_call_reporting/sms_and_mms_message_filtering/) requirements.

PS: I'm not an Apple Developer, so I won't be able to assist you with any Xcode-related issues. Please search online and share your experience as a GitHub issue with other users.


Resources:

- https://developer.apple.com/documentation/sms_and_call_reporting/sms_and_mms_message_filtering
- https://developer.apple.com/videos/play/wwdc2022/110341/
- https://devstreaming-cdn.apple.com/videos/wwdc/2017/249alewpia5158ow5k/249/249_filtering_unwanted_messages_with_identity_lookup.pdf