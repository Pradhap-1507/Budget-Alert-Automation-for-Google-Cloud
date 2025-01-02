Features
1. Budget Threshold Monitoring: Monitors thresholds such as 50%, 70%, 85%, 100%, and more.
2. Slack Notifications: Sends alerts to a specified Slack channel when thresholds are crossed.
3. Duplicate Alert Prevention: Uses a state file in Google Cloud Storage to track already triggered thresholds.
4. Monthly Refresh: Automatically resets the state file at the beginning of each month to ensure fresh alerts.

Workflow
1. Pub/Sub Trigger: The script is triggered by a Pub/Sub message containing budget event details.
2. Threshold Validation: It checks if the current budget exceeds predefined thresholds.
3. Slack Alert: Sends an alert message to Slack with details like current cost, budget amount, and threshold crossed.
4. State Management: Updates the state file in Google Cloud Storage to avoid duplicate alerts for the same threshold within the same month.

Configuration
1. Google Cloud Storage: Used to store the state file (triggered_thresholds.json).
2. Pub/Sub: Configured to send budget alert events to the script.
3. Slack Webhook URL: Configured to send notifications to the desired Slack channel.
