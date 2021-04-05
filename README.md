<div align="center">

<img src="https://raw.githubusercontent.com/loggicat/Loggicat-Server-Wiki/main/public/loggicatCloud.png" height="300" />

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

## Security Rules

There are two types of security rules <br />
<img src="https://github.com/loggicat/Loggicat-Cloud-Wiki/blob/main/public/builtinrules1.PNG" height="250" />

- **Builtin rules** : 
Pre-defined rules created by Loggicat Engine, users can choose to enable/disable builtin rules.<br />
Builtin rules can be found in "Manage Security Rules" -> "Built-in Security Rules".
- **Custom rules** : When the token/secret you are using is not in the builtin rules, users should reach out to us using the "Contact us" button in the builtin rules tab. Before new rules are created, users can choose to create some temporary regex rules in "Manage Security Rules" -> Custom Security Rules".<br />
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

## Allowlists
Loggicat handles false postivies or acceptd risks by using allowlists. <br />
- **Ignore list**: Accepting the risk, once a keyword/finding is ignored, future matches from the same security rule will be ignored. Ignore should be used on **false positives**.
- **Redact list**: Similar to ignore list, future matches to the items on the redact list will not be reported, the finding will be redacted instead. Redact should be used for **non false positives**.

There are two ways to add a new item to allowlists.
1. Added from "Findings", users will not be able to change the keyword in this case
<img src="https://github.com/loggicat/Loggicat-Cloud-Wiki/blob/main/public/allowlist1.PNG" />
Ignore Popup:
<img src="https://github.com/loggicat/Loggicat-Cloud-Wiki/blob/main/public/allowlist3.PNG" height="200"/>
Redact Popup: Loggicat currently supports 5 patterns to redact findings
<img src="https://github.com/loggicat/Loggicat-Cloud-Wiki/blob/main/public/allowlist4.PNG" height="200"/>

2. Added from "Manage Security Rules"
<img src="https://github.com/loggicat/Loggicat-Cloud-Wiki/blob/main/public/allowlist2.PNG" height="300" />
Ignore Popup:
<img src="https://github.com/loggicat/Loggicat-Cloud-Wiki/blob/main/public/allowlist5.PNG" height="200"/>
Redact Popup: 
<img src="https://github.com/loggicat/Loggicat-Cloud-Wiki/blob/main/public/allowlist6.PNG" height="200"/>

_Items added to whitelists can be edited or removed from "**Manage Allowlist**"_

## Findings
Security findings from both builtin rules and custom rules can be audited/triaged from the "Findings" tab on the sidebar.<br />
Click on a row to expand to view more information

## Scan Test
With the Scan Test feature, users are able to try out Loggicat Engine eaisly without setting up the Loggicat Watcher.<br />
<img src="https://github.com/loggicat/Loggicat-Cloud-Wiki/blob/main/public/scantest1.PNG" height="200"/>

Sample text:
```
this is my line 1
this is my line 2
this is my line 3 but with an AWS access key AKIAIOSFODNN7EXAMPLE
```
Result: <br />
<img src="https://github.com/loggicat/Loggicat-Cloud-Wiki/blob/main/public/scantest2.PNG" height="400"/>

_Noted: nothing will be stored/logged on Loggicat Cloud using Scan Test, so feel free to put some real logs there to see how it works_

---

# Watcher Management
In order to leverage all features on Loggicat Cloud, a Loggicat Watcher must be used, Watcher Management is to monitor watcher activities and generate refresh tokens.

---

# Integrations
**All tokens/secrets/webhooks mentioned in this section are encrypted on Loggicat Cloud.**<br />
**Loggicat Cloud will never return plaintext secrets/token back to users, neither from UI or APIs.**<br />
Loggicat has integrated Github and Slack, other integrations(including Gitlab, Jira, Jenkins, etc.) are under development and will be released in the future.

## Github
Github integration turns a line of logs to the exact code location, this can help developers to fix issues much faster. <br />
_Noted that : Github Code search/scan and commit monitoring are not released yet._ <br />

In order to use Github integration, a <a href="https://docs.github.com/en/github/authenticating-to-github/creating-a-personal-access-token">Github Personal Access Token</a> must be created and stored on Loggicat. <br />
Following scopes are required : 
  - Full access to repos, this is required in order to scan and search in private repos. public_repo if only for public repos
  - read:org 
<img src="https://github.com/loggicat/Loggicat-Cloud-Wiki/blob/main/public/github1.PNG" height="200"/>

Github Tokens should be added from the "Github Integration" tab and a name must be provided. <br />

<img src="https://github.com/loggicat/Loggicat-Cloud-Wiki/blob/main/public/github2.PNG" height="200"/>
In this page, you can choose to add/remove/enable/disable Github tokens, the "Test" button will validate the entered Github token and return a list of repos. </ br>

Once at least one token is added to Loggicat Cloud, now users can go to "Findings" tab and trigger a scan manually. <br />
<img src="https://github.com/loggicat/Loggicat-Cloud-Wiki/blob/main/public/github3.PNG" height="200"/>

_Noted that : Scans will be triggered automatically for newly added findings._ <br />

Users might see following Github search status:
  - Not started : A job has been been created, a manual scan might be needed
  - Pending : A job has been created and will be triggered soon
  - Owner Infomation Found : Search is done and Loggicat has found the owner
  - Owner Infomation Not Found : Search is done and Loggicat has not found the owner
  - No Github token available : No Github tokens to use
  - Invalid Gtihub tokens or Invalid confidence setting : Expired Github tokens

Once the result is ready, users can click on the "Display Owner Information" button(as shown in the previous paragraph) to view owner information. <br />
<img src="https://github.com/loggicat/Loggicat-Cloud-Wiki/blob/main/public/github4.PNG" height="200"/>

Confidence is used to measure the accuracy, when the returned infomration seems irrelevant, raise the confidence level. When Loggicat can't find any owner information for many of the findings, try lower the confidence level. <br />
The default confidence is 70% and is configurable in "Github Integration" -> "Github Integration Settings" <br />
<img src="https://github.com/loggicat/Loggicat-Cloud-Wiki/blob/main/public/github5.PNG" height="200"/>


## Slack

---

# Important Notes
1. disable non-nessccary rules
2. always keep generic rules on

---

# Questions
