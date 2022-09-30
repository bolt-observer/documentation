# Opsgenie

We assume that users already have an account on Opsgenie and are familiar with the tool. If not, details information can be found on [Opsgenie support](https://support.atlassian.com/opsgenie/)

## Account configuration

Once you have logged in to your account, make sure you first create a team.

![Untitled](https://user-images.githubusercontent.com/100695254/176128120-547d8ded-9db8-41f3-a847-25de13089e42.png)

Give a name to your team, add all members’ emails and click “Add team”.

![Untitled (1)](https://user-images.githubusercontent.com/100695254/176128327-5a3e23ce-1d76-4395-924f-7c5497c7128f.png)

The team has now been created and needs to be configured.

![Untitled (2)](https://user-images.githubusercontent.com/100695254/176128500-8e9c7f39-d72d-4d56-abfd-53043bdf7317.png)

## API Integration

On the sidebar menu, click on “Integrations” and then click on the button “Add integrations”

![Untitled (3)](https://user-images.githubusercontent.com/100695254/176128940-258f7e84-f408-4e75-8aae-38335d8f73f3.png)

Search for “API” at the top and select “API” with the ⚙️ icon

![Untitled (4)](https://user-images.githubusercontent.com/100695254/176129046-c255f268-dfa5-4d2e-984c-65505f46b9d7.png)

Configure your REST API by ticking the “Read Access”, “Create and Update Access” and “Enabled” boxes. Don't forget to press the “Save Integration” button.

![Untitled (5)](https://user-images.githubusercontent.com/100695254/176129198-34a7ecb4-6175-468c-a105-1ef0d825c2fd.png)

## Alert creation

On the top menu, click on the alert and create a new alert referring to the API recently created.

![Untitled (6)](https://user-images.githubusercontent.com/100695254/176129675-30bf29bc-bbb8-4ad7-adf7-d631b9154959.png)

Make sure you reference the API recently created, in our case “LN\_Node\_team\_API”. The alert can also be configured by adding a message, a priority, and a list of responders.

![Untitled (7)](https://user-images.githubusercontent.com/100695254/176129828-c5bc3630-dea0-4059-a0ff-900c5a6f250e.png)

In the section “Alerts”, you can see a new alert created.

![Untitled (8)](https://user-images.githubusercontent.com/100695254/176129938-afbb6848-5d01-4a6a-84df-6b3095c56c5b.png)

## Integration in bolt.observer

In the “Teams” section, click on your team “LN\_node\_team”.

![Untitled (9)](https://user-images.githubusercontent.com/100695254/176130086-21f0b870-84d5-4e6d-acea-8188d3894561.png)

In the sidebar menu, click on “Integrations” and then, click on the API you recently created.

![Untitled (10)](https://user-images.githubusercontent.com/100695254/176130532-3d597ca3-f143-406b-a071-e1ab904100cc.png)

From the field “API Key”, copy the key in the clipboard.

![Untitled (11)](https://user-images.githubusercontent.com/100695254/176130666-06bbe30b-6ab3-4e31-8f96-9b25da8a435e.png)

In [bolt.observer](http://bolt.observer/), click on “Add new alert” and select “Opsgenie” alert type. Paste the key in the field “API Key” and select your region. Don't forget to press the “Save” button.

![Untitled (12)](https://user-images.githubusercontent.com/100695254/176130806-5a336983-b051-40e8-9e09-e1c864a4ada6.png)

Make sure your alert and integration work properly by clicking on “test”. A message “Alert sent” should appear at the bottom of your screen and you should receive an alert message on your email (or other notification method chosen)

![Untitled (13)](https://user-images.githubusercontent.com/100695254/176130930-c1d56aeb-e559-40bc-9bc6-40dd517bd15d.png)
