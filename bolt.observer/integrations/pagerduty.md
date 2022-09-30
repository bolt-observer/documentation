# PagerDuty

## Pagerduty configuration

Create a service

![Untitled](https://user-images.githubusercontent.com/100695254/176686749-29aa2020-f882-4f6b-b8ed-d555880b583c.png)

Fill in the name and a description then click “Next”.

![Untitled (1)](https://user-images.githubusercontent.com/100695254/176686858-1db54d23-2e94-4bec-a097-87267c3dec89.png)

Select your escalation policy based on your needs

![Untitled (2)](https://user-images.githubusercontent.com/100695254/176686956-7c2086a2-b890-4710-881e-cc23881529ae.png)

![Untitled (3)](https://user-images.githubusercontent.com/100695254/176687036-2fea82ff-97ca-4d9b-9af7-c80539302632.png)

Select the integration. In our case, select “Events API” V2 and do not forget to click on “Create service”

![Untitled (4)](https://user-images.githubusercontent.com/100695254/176687186-3c8b492b-b9af-4027-bf42-639a66ce119a.png)

The next screen will take you to the integrations settings. From the right-hand side of the page, copy the Integration Key into the clipboard.

![Untitled (5)](https://user-images.githubusercontent.com/100695254/176687354-729363ef-8965-402f-941b-7b2cffda187a.png)

## Integration in bolt.observer

Paste the key into the field “Routing Key”, select the region and save.

⚠️ Make sure you enter the same region as you one you defined in your profile on Pagerduty (us or eu)

![Untitled (6)](https://user-images.githubusercontent.com/100695254/176687576-1bcb561d-91eb-4fd3-b5e0-c144a33cbf74.png)

You can check that the integration works properly by clicking on Test. You should see the message “Alert sent” appear as shown below.

![Untitled (6)](https://user-images.githubusercontent.com/100695254/176687677-2f0f87d0-465a-4e8d-8dea-24eaec2a6718.png)
