# webMethods CloudStreams Provider for Esendex
This project provides a sample webMethods CloudStreams Provider Project for Esendex. The following APIs are available:
* **Send SMS:** The Message Dispatcher resource can be used to send one or more SMS messages. These can be sent either straight away or scheduled for the future. https://developers.esendex.com/api-reference#messagedispatcher
* **Message Information:** The Message Information resource can be used to obtain information for one or more messages to help understand the costs involved in sending those messages. https://developers.esendex.com/api-reference#messageinformation
* **Accounts:** This operation will return a response containing summary information on all of the Esendex accounts that the user has permissions to use. https://developers.esendex.com/api-reference#accounts
* **Message Batch:** The Message Batch resource can be used to query the batches of messages which have been sent from an Esendex account. A common use of the message batch resource is to retrieve a summary of the status codes for the messages in a batch which indicates the delivery progress. Any message batches scheduled to be sent in the future can also be cancelled. https://developers.esendex.com/api-reference#messagebatch
* **Message Header:** The Message Header resource can be used to query messages which have been sent from an Esendex account. It also allows individual messages to be queried for more details. https://developers.esendex.com/api-reference#messageheader
* **Send Voicemessage:** Esendex's REST API supports the ability to send voice messages. https://developers.esendex.com/api-reference#sendvoicemessage

## Requirements

The project was developed and tested on the following installation:
1. Integration Server 9.12
2. CloudStreams Server 9.12
3. Software AG Designer 9.12 with Service Development and CloudStreams Development

## Quick start

To install the project on your local development environment follow these steps.

### Prepare CloudStreams connection

1. In Software AG Designer open ```Window > Preferences```.
2. Navigate to ```Software AG > CloudStreams Servers```.
3. Add your local Integration Server. If there is already an entry make sure username and password are correct by clicking the Test button.

### Import CloudStreams Provider Project

1. In Software AG Designer switch to the ```CloudStreams Development``` perspective.
2. Select File > Import and choose ```Software AG > CloudStreams Provider Project```. Click Next.
3. Select the root of this repository as the Root Directory.
4. Select the ```Esendex``` project.
5. Check ```Copy project into workspace```.
6. Click Finish.
7. Expand the newly imported project.
8. Right-click ```com.softwareag.esendex``` and select Deploy.

### Import Integration Server packages
The CloudStreams Provider Project does not contain neccessary doctypes.

1. Copy Esendex.zip and EsendexTests.zip to ```<install_dir>/IntegrationServer/instances/<instance>/replicate/inbound```.
2. Open Integration Server Administration in your browser.
3. Install both packages with ```Install Inbound Releases``` in Package Management.

### Add Esendex Username and Password and activate connection

To access Esendex a username and password is neccessary. Generate your Esendex Trial account here: https://developers.esendex.com/.

1. Open Integration Server Administration in your browser.
2. Navigate to ```Solutions > CloudStreams > Providers > Esendex```.
3. Select ```com.softwareag.esendex``` from the Connector List.

You will find one (disabled) connection: wmesendexTests:connection. You need to modify this connections:
1. Click the Edit button of the connection.
2. Enter your username and password and save the changes.
3. Enable the connection.

### Run tests

1. In Software AG Designer switch to the ```Service Development``` perspective.
2. Expand the ```EsendexTests``` package.
3. Run the ```*Test``` flow services you find in the subsequent directories.
______________________
These tools are provided as-is and without warranty or support. They do not constitute part of the webMethods product suite. Users are free to use, fork and modify them, subject to the license agreement. While Software AG welcomes contributions, we cannot guarantee to include every contribution in the master project.
_____________
Contact us at [TECHcommunity](mailto:technologycommunity@softwareag.com?subject=Github/SoftwareAG) if you have any questions.
