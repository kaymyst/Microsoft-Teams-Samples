---
page_type: sample
description: Samples to create "Custom Bots" to be used in Microsoft Teams.
products:
- office-teams
- office
- office-365
languages:
- javascript
extensions:
  contentType: samples
  createdDate: "12/05/2017 06:03:13 PM"
urlFragment: officedev-microsoft-teams-samples-outgoing-webhook-nodejs
---

# Outgoing webhook

This project is an implementation of a very simple [Outgoing Webhook](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/custom-bot) for Microsoft Teams. All it does is verify that what's sending messages matches the Outgoing Webhook that was created in Teams, and it echoes back whatever is sent to it.

## Steps to run locally

### Prerequisites

* Install Git for windows: https://git-for-windows.github.io/

* Clone this repo:
  ```bash
  git clone https://github.com/OfficeDev/msteams-samples-outgoing-webhook-nodejs.git
  ```

* Install Node: https://nodejs.org/en/download/    

* Install a tunnelling service. These instructions assume you are using ngrok: https://ngrok.com/

* Start the tunneling service, e.g. `ngrok http 8080` and copy the https:// URL it generates to the clipboard, e.g. https://2fb7b5e8.ngrok.io

* Create the Outgoing Webhook in Teams using the instructions [here](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/custom-bot). Paste the tunneling service URL from the previous step into the "Callback URL" box. After you press the Create button, copy/paste the security token that Teams generates to the clipboard.

* Paste the security token generated by Teams as the value of `sharedSecret` in `app.js`. When you're done, it should look something like this:

  ```javascript
  const sharedSecret = "+ZaRRMC8+mpnfGaGsBOmkIFt98bttL5YQRq3p2tXgcE=";
  ```

* In the directory in which you installed this project, type `node app.js`

* In Microsoft Teams, in any channel in the team in which you created the Outgoing Webhook, you can type `@<botname> <card-type>` then it will respond back a card with specified card type.
  
  Supported <card type>: "adaptive-card", "hero-card", "list-card", "o365-card", "thumbnail-card"

Example screenshot to show Hero card:
![Hero card](Images/heroCard.png)

* If you type anything else apart from above mentioned type, it will echo back what you typed.

Example screenshot to show Echo message:
![Echo message](Images/echoMessage.png)

## Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.microsoft.com.

When you submit a pull request, a CLA-bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., label, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.
