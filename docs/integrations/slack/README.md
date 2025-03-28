# Slack Integration

Operations can also be triggered directly from Slack, offering users convenience and visibility to track executions. You can assign specific operations to desired Slack channels, enabling better organization and reducing confusion.

## Setting up a Slack Project

### 1. Create a Slack Project:

Start by creating a Slack project.

![Slack](/docs/images/CreateProject.gif)

### 2. Connect to Slack:

Link your project to Slack and grant the necessary permissions to access your Slack workspace.

![Slack](/docs/images/ConnectSlack.png)
![Slack](/docs/images/AllowSlack.png)

### 3. Configure the Slack Project: 

Assign a Slack channel to the project and specify the allowed commands, connections, and workflows for that channel.

![Slack](/docs/images/SlackProject.gif)

## How to trigger Operations via Slack?

Commands can be executed in Slack as shown in the example execution below:

**cc:** Refers to the connection.

**workspace-delete:** The command being executed.

**--env and --email:** Arguments, followed by their respective values.

![Slack](/docs/images/slackexec.png)
