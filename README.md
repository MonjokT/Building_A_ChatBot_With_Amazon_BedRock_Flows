# Customer Support Chatbot with Amazon Bedrock Flows

An AI-powered customer support chatbot built on AWS using Amazon Bedrock Flows. This project routes customer requests to the appropriate support path, answers FAQ-style questions, captures bug reports, and handles unsupported requests through a structured fallback flow.

## Overview

The goal of this project was to design and validate a cloud-based generative AI support workflow that can:
- classify incoming customer requests
- route users to the correct support experience
- answer common FAQ questions
- collect and store bug reports
- respond appropriately to unsupported requests

The solution uses prompt-based intent classification within Amazon Bedrock Flows and integrates AWS services to support a practical customer support use case.

## Features

- Intent-based routing using Amazon Bedrock Flows
- FAQ handling for supported customer questions
- Bug report intake workflow
- Structured bug report storage in DynamoDB
- Fallback handling for unsupported or out-of-scope requests
- Manual scenario testing across multiple support paths
- LLM-based evaluation using Amazon Bedrock evaluation tools

## Architecture

At a high level, the chatbot workflow follows this pattern:

1. A user submits a support request
2. The flow classifies the request type
3. The request is routed to one of several paths:
   - FAQ support
   - bug reporting
   - unsupported request fallback
4. Bug reports are stored in DynamoDB
5. Responses are tested and evaluated for correctness

## Tech Stack

- Amazon Web Services (AWS)
- Amazon Bedrock
- Amazon Bedrock Flows
- Amazon DynamoDB
- Python

## Testing and Evaluation

The project was validated through both manual testing and automated evaluation.

### Manual Testing
The chatbot was tested against multiple customer support scenarios, including:
- covered FAQ requests
- uncovered FAQ requests
- bug report submissions
- unsupported or unrelated requests

### Evaluation
Amazon Bedrock evaluation was used with:
- evaluation type: LLM-as-a-judge
- metric: correctness

The evaluation results showed a correctness score close to 1, indicating that the chatbot responses aligned well with expected outputs across the tested scenarios.

## Project Structure

```text
project/
├── README.md
├── evidence/
│   ├── flow screenshots
│   ├── routing screenshots
│   ├── FAQ screenshots
│   ├── bug report screenshots
│   └── evaluation results
└── starter/
    ├── Python scripts
    ├── CloudFormation templates
    ├── prompt files
    └── test and evaluation assets
