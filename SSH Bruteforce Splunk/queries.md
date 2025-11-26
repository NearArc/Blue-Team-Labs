# Splunk SPL Queries – SSH Brute Force Detection

---

## 1. Extract SSH Authentication Events
index=* (sshd OR "authentication failure")

---

## 2. Failed SSH Logins
index=* "Failed password" OR "authentication failure"
| stats count by src, user
| sort - count

---

## 3. Top Attacking IPs
index=* "Failed password"
| stats count by src
| sort - count

---

## 4. Attempted Usernames
index=* "Failed password"
| rex "Invalid user (?<user>\w+)"
| stats count by user
| sort - count

---

## 5. Unknown User Attempts
index=* "Invalid user"
| rex "Invalid user (?<user>\w+)"
| stats count by user

---

## 6. SSH Failures Over Time
index=* "Failed password"
| timechart span=1m count

---

## 7. Attacking IP Activity Timeline
index=* "Failed password"
| timechart span=1m count by src

---

## 8. Successful Logins Check
index=* "Accepted password"
| stats count by user, src
