**Datadog Administrator & Developer — Hands-On Interview Prep Tasks
**
Sign up for a free Datadog trial (14 days, no card needed for trial) before starting: https://www.datadoghq.com/free-datadog-trial/

Task 1: Install and Configure the Datadog Agent

Objective: Prove you can deploy and troubleshoot the core agent — the most basic real-world admin task.

Steps:

Spin up a Linux VM (can reuse your free-tier EC2 instance).
Get your Datadog API key: Datadog UI → Organization Settings → API Keys.
Install the agent:
   DD_API_KEY=<your_key> DD_SITE="datadoghq.com" bash -c "$(curl -L https://install.datadoghq.com/scripts/install_script_agent7.sh)"
Verify it's running: sudo datadog-agent status
Check the config file: sudo nano /etc/datadog-agent/datadog.yaml — note key settings like api_key, site, tags.
Confirm the host shows up in Datadog UI → Infrastructure → Host Map within 1-2 minutes.
Restart the agent and know the command: sudo systemctl restart datadog-agent

Likely interview question: "How do you troubleshoot an agent that isn't reporting?" → Know: check datadog-agent status, check /var/log/datadog/agent.log, verify API key/network connectivity/proxy settings.


Last login: Fri Jul 31 02:21:18 on ttys000
Apple@MacBook-Pro ~ % ls       
AWSCLIV2.pkg	Desktop		Documents	Downloads	Library		Movies		Music		Pictures
Apple@MacBook-Pro ~ % chmod 400 Downloads/datadog-key.pem 
Apple@MacBook-Pro ~ % ssh -i Downloads/datadog-key.pem ec2-user@54.167.88.46
The authenticity of host '54.167.88.46 (54.167.88.46)' can't be established.
ED25519 key fingerprint is: SHA256:bSkABoZeYoB6Nj+nrvp1jTZtaHRPYweMtzLUU/H+npU
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '54.167.88.46' (ED25519) to the list of known hosts.
   ,     #_
   ~\_  ####_        Amazon Linux 2023
  ~~  \_#####\
  ~~     \###|
  ~~       \#/ ___   https://aws.amazon.com/linux/amazon-linux-2023
   ~~       V~' '->
    ~~~         /
      ~~._.   _/
         _/ _/
       _/


/home/ec2-user
[ec2-user@ip-172-31-26-192 ~]$ DD_API_KEY=092b5c8f1a888888115 DD_SITE="datadoghq.com" bash -c "$(curl -L https://install.datadoghq.com/scripts/install_script_agent7.sh)"




Troubleshooting steps for Datadog agent failures

Check overall agent status
Run: sudo datadog-agent status — this is your first stop. It shows whether the agent process is running, whether the API key is valid, which checks are OK/failing, and any component-level errors (you already saw this output).
2
Check the service status at the OS level
Run: sudo systemctl status datadog-agent — shows whether the underlying service is active, stopped, or crashing/restarting repeatedly. Look for 'active (running)' vs 'failed' or 'inactive'.
3
Read the recent log lines
Run: sudo tail -100 /var/log/datadog/agent.log — shows the last 100 lines of the main log, where startup errors, connection failures, or config parsing errors usually show up first.


4
Watch the log live while restarting
Run: sudo tail -f /var/log/datadog/agent.log — keeps the log open and streaming live. Useful if you want to restart the agent and watch exactly what happens in real time.
5
Restart the agent
Run: sudo systemctl restart datadog-agent — restarts the agent service. Do this while step 4's tail -f is running in a second terminal/tab so you catch any errors during startup.
6
Validate your configuration files
Run: sudo datadog-agent configcheck — validates your YAML config files (datadog.yaml and everything in conf.d) and flags syntax errors or misconfigured checks before they even try to run.



7
Run the built-in diagnostic tool
Run: sudo datadog-agent diagnose — runs Datadog's built-in self-diagnostic suite: checks connectivity to Datadog's servers, verifies the API key, checks port availability, and more, all in one command with pass/fail output.
8
Test raw network connectivity to Datadog
Run: curl -v https://app.datadoghq.com — confirms your instance can actually reach Datadog's servers over the network. If this hangs or fails, it's a security group / firewall / DNS issue, not an agent problem.

Task 2: Enable an Integration (e.g., AWS or NGINX)

Objective: Show you understand integrations, which is core to "administrator" work.

Steps:

Datadog UI → Integrations → search "Amazon Web Services" → click it.
Follow the IAM role setup: create an IAM policy with Datadog's required read-only permissions, create a role, and add Datadog's AWS account ID as trusted.
Paste the Role ARN into Datadog's AWS integration tile.
Alternatively (simpler, faster for practice): install the NGINX integration on your Linux VM — enables the nginx check in /etc/datadog-agent/conf.d/nginx.d/conf.yaml.example, rename to conf.yaml, restart agent.
Confirm metrics start flowing: Datadog UI → Metrics → Explorer → search nginx.net.request_per_s (or aws.ec2.cpuutilization if you did AWS).

Likely interview question: "Difference between agent-based and API-based (crawler) integrations?" → Agent-based needs the Datadog Agent installed on the host; API-based (like AWS) polls cloud provider APIs directly, no agent needed on each resources
