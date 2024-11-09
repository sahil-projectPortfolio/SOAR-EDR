For the host machines, you can use AWS EC2 instance (or any CSP) or use Virtualisation (Oracle Virtualbox) to run Windows/Linux.

<b>Set Up an EC2 Instance</b>

Step 1: Log in to AWS Console
https://aws.amazon.com/console/.
Log in with your credentials.

Step 2: Launch an EC2 Instance in AWS Console, choose an Amazon Machine Image (AMI) and select a base image for the instance(Windows/linux)

Step 3: Choose the instance type- t2.micro (as it is free tier) and configure Instance Details by leaving most of the default settings. 
(ENSURE you have a public IP address to access the instance remotely)

Step 4: Allow SSH (port 22) for remote access. Ensure HTTP (port 80) and HTTPS (port 443) are open. 
Once all is done launch the instance.

<b>Set Up LimaCharlie</b>

Step 1: Create a LimaCharlie Account
https://limacharlie.io/.

Step 2: Set Up a New Organization
Once logged in, Create Organization and set the initial configurations.

<b>Set Up Tines</b>
 
Step 1: Sign Up for Tines
https://www.tines.com

Step 2: click New Story to create a new workflow automation for incident response.
Name your story (e.g., "SOAR Incident Response").

<b>Setup Slack for Alerts</b>

Step 1: Create a Slack Workspace at https://slack.com.
Create a new workspace.

Step 2: Create a Slack Channel for Alerts
Create a dedicated channel (e.g., #security-alerts) where Tines will send alerts based on LimaCharlie events.


<b>Setup Virustotal for Hash lookup</b>
Step 1: Go to https://www.virustotal.com
Step 2: Sign in, or create an account if new user
Step 2: Visit my account and check for API key or token.