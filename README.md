# Smart Customer Support Chatbot with Amazon Bedrock

An automated customer service system built as part of the **AWS AI/ML / Future Agent Engineer** program. This project orchestrates an intelligent customer support workflow that handles standard FAQs, routes general requests, and automatically logs customer bug reports into a secure database using serverless tools.

## 🚀 What It Does
* **Answers FAQs:** Instantly responds to customer questions about shipping, orders, returns, and payments using embedded product documentation.
* **Logs Bug Reports:** Automatically captures technical issues, extracts necessary details (like description, steps to reproduce, and environment), and saves them as tickets in a cloud database via AWS Lambda[cite: 1].
* **Smart Routing:** Directs user messages down the correct processing path using Amazon Bedrock conditional logic nodes.

---

## 📋 Project Overview & Resources Provided
To complete this challenge, the following core assets and setup files were utilized:
* `create_bug_report` - A custom backend tool built to store support tickets[cite: 1].
* `online_shop_faq.md` - The reference FAQ document used by the chatbot to answer user inquiries[cite: 1].

### Project Files Layout
| File / Folder | Description |
|------|-------------|
| `docs/tools-setup.md` | Step-by-step walkthrough for deploying the bug report tool and database[cite: 1]. |
| `docs/testing.md` | Guide for running automated test suites and Bedrock evaluations[cite: 1]. |
| `cloudformation-tool.yaml` | Infrastructure template used to spin up the bug-reporting Lambda function and DynamoDB table[cite: 1]. |
| `cloudformation-testing.yaml` | Template used to deploy testing resources[cite: 1]. |
| `lambda/create_bug_report.py` | Python script handling ticket storage logic in Amazon DynamoDB[cite: 1]. |
| `evaluation/` | Test datasets (`.jsonl`) and automated evaluation output metrics[cite: 1]. |
| `evidence/` | Verification screenshots confirming successful database writes and routing paths[cite: 1]. |

---

## 🛠️ Technologies Used
* **Amazon Bedrock Flows & Agents:** Orchestrates the multi-branch chat logic, prompt nodes, and automated tool use.
* **AWS Lambda (Python):** Serverless backend integration that processes and saves bug tickets[cite: 1].
* **Amazon DynamoDB:** Secure NoSQL database storing customer support and bug tickets[cite: 1].
* **Amazon Bedrock Evaluations:** Automated "LLM-as-a-judge" evaluation framework used to measure chatbot accuracy and response quality.

---

## 📊 Testing & Verification
The system was rigorously tested across multiple functional branches (FAQs, bug submissions, and general fallback routing) to ensure high reliability and low latency. 

### Key Verification Highlights:
* **Bug Saved in Database:** `evidence/04-dynamodb-bug-report-item.png`[cite: 1]
* **FAQ Path Test Coverage:** `evidence/07-flow-test-uncovered-faq.png`[cite: 1]
* **General Request Routing:** `evidence/08-flow-test-other-request.png`[cite: 1]
* **Final Chat Transcript:** `evidence/10-bug-report-chat-transcript-final.png`[cite: 1]

---

## 📚 Official AWS References & Guides
If you want to learn more about the underlying AWS services and architectural patterns used in this project, check out these official resources:
* [Amazon Bedrock Flows Documentation](https://docs.aws.amazon.com/bedrock/latest/userguide/flows.html) – Learn how to build multi-step conversational workflows[cite: 1].
* [Amazon Bedrock Agents Guide](https://docs.aws.amazon.com/bedrock/latest/userguide/agents.html) – Discover how foundation models safely invoke external tools and APIs[cite: 1].
* [Amazon Bedrock Model Evaluation](https://docs.aws.amazon.com/bedrock/latest/userguide/evaluation.html) – Read up on automated and human-in-the-loop evaluation metrics[cite: 1].
* [AWS Lambda Developer Guide](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) – Explore serverless function development with Python[cite: 1].
* [Amazon DynamoDB Getting Started](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Introduction.html) – Learn NoSQL table design and management[cite: 1].

---

## 🧹 Cleanup
To avoid ongoing cloud resource charges, the deployed CloudFormation stacks can be safely removed using the AWS CLI:
```bash
aws cloudformation delete-stack --stack-name bug-report-tool-stack --region us-east-1
aws cloudformation delete-stack --stack-name bug-report-testing-stack --region us-east-1

👤 Author & Acknowledgments
Author: Monjok Terem

Acknowledgments: Built as part of the AWS AI/ML / Future Agent Engineer program curriculum[cite: 1].
