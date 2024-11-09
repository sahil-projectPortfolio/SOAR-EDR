<b>LimaCharlie to Host Machine</b>
(Windows Machine)
1. Download the LimaCharlie agent from the Deploy Agents section in LimaCharlie’s dashboard and follow the instructions for installing the agent on a Windows machine.

2. Under Sensors, you should see the agent you deployed listed with the status Connected, conforming LimaCharlie is now monitoring the host machine for any incidents.

3. Create Detections and Response rule for detections (use lazagne as the telemetry).

<b>Integrate LimaCharlie with Tines</b>
1. go to Settings > API Keys.
Create a new API key for Tines integration:
Provide it with Read and Execute permissions to access events and responses.

2. In Tines, go to your new story and add a new Action:

3. Action Type: Webhook action.
It would retrive events detection from LimaCharlie.
Go to Outputs in Limacharlie, then select Detections>Tines and enter name and the Destination Host (Webhook link).

<b>Integrate Tines to slack for alerts</b>
1. Within your workspace, create a new channel for alerts (e.g., #security-alerts).

2. Copy the Channel ID and add it to credentials in Tines to send all the alerts, link and messages to the dedicated channel.

3. Choose Slack in the Tines story, Use message details to fill the body.and link Webhook to Slack (not the other way around!). This enables your channel to start recieving detections.

<b>Integrate Tines to email for alerts</b>
1. Action Type: send Email.
Fill the test/temporary email and link Webhook to it.
Use message details to fill the body.
The detections will now will also be sent on given email

<b>Create user prompt</b>
1. Action Type: Tools>Page and name it User prompt and fill out description.

2. Edit the page by adding boolean option of yes or no to isolate, along with the details of the detected event. (use message details) and link the Webhook to the User prompt page.

<b>Integrate User prompt result (no) to Tines story</b>
1. Choose Action Type: Trigger

2. Under Rules section, enter user_prompt.body.isolate
is equal to; false

3. Link the user prompt to Trigger, and Trigger to slack with message 'Computer not isolated, please investigate immediately'

<b>Integrate User prompt result (yes) to Tines story</b>
1. Choose Action Type: Trigger

2. Under Rules section, enter user_prompt.body.isolate
is equal to; true

3. Under Templates in Tines, search for Limacharlie and add it to story.
In Limacharlie, select Isolate sensor (For host isolation)

4. Edit the URL section and add the path to Sensor ID: <<retrieve_detections.body.detect.routing.sid>> and link the Trigger to the Limacharlie template.

5. Connect it to Limacharlie by adding new credential. Copy the Org JWt.
It's present in the Access Management>REST API.
Paste it in the value, followed by *.limacharlie.io in domain section.

<b>Integrate the isolation status</b>
1. Under Templates in Tines, search for Limacharlie and add it to story.
In Limacharlie, select Isolate status.

2. Enter the following detail in URL Section https://api.limacharlie.io/v1/<<retrieve_detections.body.detect.routing.sid>>/isolation

3. Add slack, and display the 'isolated successfully' message, along with isolation status. Link the Isolate sensor to Isolation status and islolation status to Slack.

<b>Integrate Virustotal</b>
The extra feature that is added is to perform a hash lookup or check has reputation. This would give more broader information about the malicious action performed on the host/end device

1. Add new credential for Virustotal by adding API, available at Virustotal user account. This establishes the connection between Tines and Virustotal.

2. Add slack and connect Webhook to it.
In message section:
Check VirusTotal file reputation:
https://www.virustotal.com/gui/file/<<retrieve_detections.body.detect.event.HASH>>
