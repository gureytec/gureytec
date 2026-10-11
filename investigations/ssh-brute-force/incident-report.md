# SSH Brute-Force Investigation

**Category:** Linux Authentication Analysis  
**Environment:** Kali Linux / Training Lab  
**Status:** Investigation in progress

## 1. Objective

Investigate repeated failed SSH authentication attempts using Linux authentication logs. Identify suspicious source IP addresses, targeted usernames, and whether any successful authentication followed the failures.

## 2. Background

SSH (Secure Shell) allows users to access and manage remote systems securely.

A brute-force attack involves repeated attempts to guess passwords or credentials. Multiple failed login attempts may indicate password guessing, but they can also result from legitimate users entering incorrect passwords.

Further investigation is required before classifying activity as a confirmed attack.

## 3. Tools Used

- Kali Linux
- Linux terminal
- `grep`
- `awk`
- `sort`
- `uniq`
- Linux authentication logs (`auth.log`)

## 4. Investigation Commands

### Search for failed SSH logins

```bash
grep "Failed password" auth.log
```

This displays authentication log entries containing the phrase `Failed password`.

### Count failed attempts by source IP

```bash
grep "Failed password" auth.log |
awk '{print $(NF-3)}' |
sort |
uniq -c
```

**Command breakdown:**

- `grep` filters failed password events.
- `awk` extracts the source IP for the expected OpenSSH log format.
- `sort` groups identical IP addresses together.
- `uniq -c` counts occurrences.

Always verify the extracted IP addresses against the original log entries before reporting the results.

## 5. Evidence and Findings

The following results were recorded during a previous training exercise. They must be verified against the original authentication logs before being treated as confirmed findings.

| **Investigation field** | **Recorded result** |
|---|---|
| Source IP address 1 | `10.10.10.25` — 5 failed attempts (verification pending) |
| Source IP address 2 | `192.168.1.50` — 3 failed attempts (verification pending) |
| Targeted usernames | To be verified |
| Subsequent successful login | `192.168.1.20` — relationship to failed attempts not established |
| Confirmed compromise | Not established |

### Preliminary Assessment

The recorded failed authentication attempts may indicate password guessing activity. However, the original logs must be reviewed to confirm the counts, identify the targeted usernames, and establish the relevant timestamps.

The successful login from `192.168.1.20` must be investigated separately. There is currently insufficient evidence to establish whether it is related to the failed attempts or whether an account was compromised.

### Recommended Next Steps

- Verify the failed-attempt counts using the original authentication logs.
- Identify the targeted usernames and timestamps.
- Investigate the successful login and determine which account was used.
- Correlate the events before deciding whether the activity represents a brute-force attack.


## 6. Investigation Process

1. Search authentication logs for failed SSH password attempts.
2. Identify the source IP addresses and targeted usernames.
3. Count the failed attempts and review their timestamps.
4. Search for successful authentication events from the same sources.
5. Review surrounding activity for evidence of unauthorized access.
6. Document findings and recommend appropriate next steps.

## 7. MITRE ATT&CK Mapping

**Technique:** [T1110 — Brute Force](https://attack.mitre.org/techniques/T1110/)

This technique may be relevant if the evidence supports password guessing or brute-force activity. Repeated failures alone do not establish malicious intent.

## 8. Recommended SOC Actions

- Review authentication activity around the suspicious events.
- Check whether any login attempts succeeded.
- Identify affected accounts and systems.
- Correlate authentication logs with other available security events.
- Escalate to the appropriate security team if compromise is suspected.
- Follow organizational procedures before blocking IP addresses or disabling accounts.

## 9. Conclusion

This investigation demonstrates a basic approach to Linux authentication-log analysis.

The final assessment must be based on verified evidence, including the frequency of failed attempts, targeted accounts, source context, and any subsequent successful authentication.

**Final classification:** Pending evidence review.

## 10. Learning Outcomes

Through this exercise, I am practicing how to:

- Search and filter Linux authentication logs.
- Extract relevant fields using command-line tools.
- Identify patterns in failed authentication attempts.
- Investigate suspicious login activity.
- Document evidence and recommend next steps.

## Disclaimer

This is an educational cybersecurity investigation conducted in a training environment. Findings will be updated as evidence is verified. No real-world compromise is claimed.
