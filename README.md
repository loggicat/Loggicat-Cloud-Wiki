<div align="center">

<img src="https://raw.githubusercontent.com/loggicat/Loggicat-Server-Wiki/main/public/loggicatCloud.png" height="200" />

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
* **[Overview](#overview)** What is Loggicat?
* **[Why Loggicat](#why-loggicat)** Why do I need Loggicat?
* **[Workflow](#workflows)** Some typical Loggicat use cases
* **[Features](#features)** Available features
* **[Integration](#integrations)** Integrate Loggicat with popular tools such as Github, Slack
* **[Important Notes](#important-notes)** Please read this section before your first login
* **[Questions](#questions)** Answers to some common questions


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
<img src="https://raw.githubusercontent.com/loggicat/Loggicat-Server-Wiki/main/public/splunk-logo-2.png" height="70" />
  
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

**Security Rules** There are two types of security rules
<img src="https://github.com/loggicat/Loggicat-Cloud-Wiki/blob/main/public/builtinrules1.PNG" height="250" />

- Builtin rules : 
Pre-defined rules created by Loggicat Engine, users can choose to enable/disable builtin rules.<br />
Builtin rules can be found in "Manage Security Rules" -> "Built-in Security Rules".
- Custom rules : When the token/secret you are using is not in the builtin rules, users should reach out to us using the "Contact us" button in the builtin rules tab. Before new rules are created, users can choose to create some temporary regex rules in "Manage Security Rules" -> Custom Security Rules".<br />
To create such rules, simply create the "Add a new rule" button.
<img src="https://github.com/loggicat/Loggicat-Cloud-Wiki/blob/main/public/customrules1.PNG" height="250" />
In order to create a custom rule, a name and a keyword must be given, keyword can be regex or just simply a string, the input text is for users to validate the keyword works as expected.
<img src="https://github.com/loggicat/Loggicat-Cloud-Wiki/blob/main/public/customrules2.PNG" height="250" />
Once a cusom rule is created, users can 

   - Enable/Disable a custom rule
   - Edit
   - Delete
   - Add a pattern to always ignore (see AllowLists section)
   - Add a pattern to always redact (see AllowLists section)
   
<img src="https://github.com/loggicat/Loggicat-Cloud-Wiki/blob/main/public/customrules3.PNG" height="250" />

**Allowlists**

**Findings**

---

# Integrations

---

# Important Notes
1. disable non-nessccary rules
2. always keep generic rules on

---

# Questions
