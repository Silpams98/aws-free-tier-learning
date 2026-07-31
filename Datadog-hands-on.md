# Datadog Administrator & Developer — Hands-On Interview Prep


## Task 1: Install and Configure the Datadog Agent

**Objective:** Prove you can deploy and troubleshoot the core agent — the most basic real-world admin task.

### Steps

1. **Spin up a Linux VM** (reused a free-tier EC2 instance).
2. **Get the Datadog API key**
   Datadog UI → *Organization Settings* → *API Keys*.
3. **Install the agent**

   DD_API_KEY=<your_key> DD_SITE="datadoghq.com" bash -c "$(curl -L https://install.datadoghq.com/scripts/install_script_agent7.sh)"
 
4. **Verify it's running**
  
   sudo datadog-agent status
 
5. **Check the config file**
   
   sudo nano /etc/datadog-agent/datadog.yaml
  
   Key settings to note: `api_key`, `site`, `tags`.
6. **Confirm the host appears**
   Datadog UI → *Infrastructure* → *Host Map* (usually visible within 1–2 minutes).
7. **Know the restart command**
  
   sudo systemctl restart datadog-agent
 

**Likely interview question:**
> "How do you troubleshoot an agent that isn't reporting?"

**Answer:** Check `datadog-agent status`, check `/var/log/datadog/agent.log`, verify API key, network connectivity, and proxy settings.

---

### Session Log — Connecting and Installing on EC2


Apple@MacBook-Pro ~ % ls
AWSCLIV2.pkg  Desktop  Documents  Downloads  Library  Movies  Music  Pictures

Apple@MacBook-Pro ~ % chmod 400 Downloads/datadog-key.pem

Apple@MacBook-Pro ~ % ssh -i Downloads/datadog-key.pem ec2-user@54.167.88.46
The authenticity of host '54.167.88.46 (54.167.88.46)' can't be established.
ED25519 key fingerprint is: SHA256:bSkABoZeYoB6Nj+nrvp1jTZtaHRPYweMtzLUU/H+npU
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '54.167.88.46' (ED25519) to the list of known hosts.

   Amazon Linux 2023
   https://aws.amazon.com/linux/amazon-linux-2023/

[ec2-user@ip-172-31-26-192 ~]$ DD_API_KEY=<redacted> DD_SITE="datadoghq.com" bash -c "$(curl -L https://install.datadoghq.com/scripts/install_script_agent7.sh)"
```

> **Note:** API key redacted here for security — never commit real API keys to a public GitHub repo. Consider rotating this key if it was ever pasted somewhere shareable.

---

## Task 2: Troubleshooting Datadog Agent Failures

A methodical, layered approach — from the agent, down to the OS, down to the network. This is the exact flow interviewers want described when they ask "walk me through debugging a silent agent."

| Step | Command | What it tells you |
|---|---|---|
| 1. Check overall agent status | `sudo datadog-agent status` | Whether the agent process is running, API key validity, per-check health |
| 2. Check the OS-level service | `sudo systemctl status datadog-agent` | Whether the service is `active (running)`, `failed`, or restarting in a crash loop |
| 3. Read recent log lines | `sudo tail -100 /var/log/datadog/agent.log` | Startup errors, connection failures, config parsing issues |
| 4. Watch logs live | `sudo tail -f /var/log/datadog/agent.log` | Real-time view — pair with a restart to catch errors as they happen |
| 5. Restart the agent | `sudo systemctl restart datadog-agent` | Resets the service; run while step 4 is active in a second terminal |
| 6. Validate configuration | `sudo datadog-agent configcheck` | Flags YAML syntax errors or misconfigured checks in `datadog.yaml` / `conf.d` |
| 7. Run built-in diagnostics | `sudo datadog-agent diagnose` | Full self-check: connectivity, API key, port availability, pass/fail summary |
| 8. Test raw network connectivity | `curl -v https://app.datadoghq.com` | Confirms the instance can reach Datadog's servers — rules out agent vs. network issue |

**Recommended troubleshooting order:**
`status → service status → logs → configcheck → diagnose → network test`

---

## Summary

This session covered the full lifecycle of a single task: **provisioning → installing → verifying → troubleshooting** — the exact narrative arc to walk an interviewer through when demonstrating hands-on Datadog Administrator/Developer experience.
