<div align="center">

<img src="https://raw.githubusercontent.com/loggicat/Loggicat-Server-Wiki/main/public/loggicatCloud.png" height="140" />

**Loggicat solves data leaks by shifting data security left**

[![Follow on Twitter](https://img.shields.io/twitter/follow/loggicat?style=social)](https://twitter.com/loggicat)

---

</div>

<h3 align="left">
For <a href="https://github.com/loggicat/Loggicat-watcher-public">Loggicat Watcher</a>
</h3>
A Loggicat Watcher acts as a connector between client machines and Loggicat Server.
<br />

---

# Getting Started With Loggicat Server
* **[Overview](https://github.com/loggicat/Loggicat-Server-Wiki/blob/main/README.md#overview)** What is Loggicat?
* **[Why Loggicat](https://github.com/loggicat/Loggicat-Server-Wiki/blob/main/README.md#why-loggicat)** Why do I need Loggicat?
* **[Workflow](https://github.com/loggicat/Loggicat-Server-Wiki/blob/main/README.md#workflows)** Some typical Loggicat use cases
* **[Features](https://github.com/loggicat/Loggicat-Server-Wiki/blob/main/README.md#features)** Available features
* **[Integration](https://github.com/loggicat/Loggicat-Server-Wiki/blob/main/README.md#integrations)** Integrate Loggicat with popular tools such as Github, Slack
* **[Important Notes](https://github.com/loggicat/Loggicat-Server-Wiki/blob/main/README.md#important-notes)** Please read this section before your first login
* **[Questions](https://github.com/loggicat/Loggicat-Server-Wiki/blob/main/README.md#questions)** Answers to some common questions


---

# Overview
**Loggicat provides a solution to data leaks and drastically decrese the detection time for such issues from months to seconds or hours.**
<br />
There are two components:
- Loggicat Cloud - A saas server to store security findings and configurations.
- Loggicat Watcher - Deployed on client machines or build machines to scan code, logs and databases.

---

# Why Loggicat
- **Seamless integration** : Loggicat will not change how you work, it can be used on top of any other tools.
- **Another layer of security** : Even if you already have an in-house solution or another tool, it is always good to have something else since there might always be some false-negatives cases in the security world
- **FREE** - Any company can request to have a few license to enjoy all the features for FREE!

---

# Workflows
Essentially Loggicat uses a smart engine to detect security issues such as plaintext secrets or PII in given text, so Loggicat can be used under many different circumstances.
<details>
<summary>
  Protecting data security in <img src="https://raw.githubusercontent.com/loggicat/Loggicat-Server-Wiki/main/public/splunk-logo-2.png" height="70" />
</summary>
<br />
Before sending local logs to Splunk, we can now have Loggicat watcher to monitor local logs first and any potential sensitive data will be extracted from the logs and sent to Loggicat Server, your splunk logs will always be clean.   
  
_Noted : Streaming mode is currentely not supproted. It will be added in the next release._
 
</details>
<details>
<summary>
  Protecting data security in <img src="https://raw.githubusercontent.com/loggicat/Loggicat-Server-Wiki/main/public/logo-jenkins.jpg" height="70" />
</summary>
<br />
Jenkins is a very power CI/CD platform especially with a vast number of plugins. However, this also introduces extra risks since a plugin might log sensitive data in plaintext. Loggicat Watcher can be configured in this case to ensure that any job console output and Jenkins logs are clean. 

</details>
<details>
<summary>
  Protecting data security in <img src="https://raw.githubusercontent.com/loggicat/Loggicat-Server-Wiki/main/public/GitHub-logo.png" height="70" />
</summary>
<br />
Loggicat watcher can scan local code for potential sensitive data.
  
_Noted :  pre-commit-hooks is currentely not supproted. It will be added in the next release. Cloud Git repo scan will also be added._

</details>

---

# Features

---

# Integrations

---

# Important Notes

---

# Questions
