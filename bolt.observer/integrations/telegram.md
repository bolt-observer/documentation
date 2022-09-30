# Telegram

### # Prerequesites

To receive alerts from our platform on telegram you need to create a [new bot on telegram](https://core.telegram.org/bots#6-botfather) (or use an existing one).

### # Step 1: Setup

Login to your account. If you haven't already done it, add a node to monitor in the “Nodes” section.

![Integration\_Step1](https://user-images.githubusercontent.com/100695254/170029396-b8b4d155-b42c-4acc-a429-61a83e62a5e2.png)

In the “Alerts” section, create a new alert and choose Telegram in the field “type”

### # Step 2: Enter bot\_key and chat ID

You are now invited to enter the bot\_key (token) and chat ID

![Integration\_Step2](https://user-images.githubusercontent.com/100695254/170029542-451c0cfa-b233-44ae-ae52-bd76a8aeea14.png)

⚠️Warning: The ID required to connect to [bolt.observer](http://bolt.observer/) is the chat ID, and it shouldn't be confused with the participants' ID.

⚠️Warning: The chat id format is a string of numbers. Example: -1001674000166

⚠️Warning: Make sure you include all characters after “:”. In the example above, “-” must be included

Once your alert is saved, it appears with other alerts that had previously been configured.

### # Step 3: Test

The last step is to make sure the flow of notifications works properly.

You can click on the test button in your Telegram alert and you should see a “message sent” at the bottom of the page informing you that the message has been sent.

![Integration\_Step3](https://user-images.githubusercontent.com/100695254/170030173-717168e3-e2a1-40bb-b252-690efce3cb87.png)

On your Telegram chat, you will receive the following message

![Integration\_Test](https://user-images.githubusercontent.com/100695254/170030473-d5d8b312-32d3-4c8a-ab85-73c26851e0de.jpg)

Et voilà! You are ready to go!
