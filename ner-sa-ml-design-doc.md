# Named Entity-Recognition & Sentiment Analysis ml-design-doc

## 1. Overview
Utilize existing pre-trained ML models for Named Entity-Recognition and Sentiment Analysis for financial news feeds.

## 2. Motivation & Success metrics
In a modern fast changing world it is important to get some hints our of real-time news feeds. Machine Learning could help with these use cases. Utilizing existing pre-trained ML models should save time / cost.     

## 3. Requirements & Constraints
We start with limited numbers of users who access system over API and limited number of news feeds. But the system should be scalable for potential grows.

### 3.1 What's in-scope & out-of-scope?
Trends, trends visualization, analytical reports are out of scope.

## 4. Methodology

### 4.1. Problem statement
TBD: Named Entity-Recognition & Sentiment Analysis 

### 4.2. Data
We assume existing pre-trained language models can be used as a starting point. We also assume public labeled data for Named Entity-Recognition & Sentiment Analysis are exists and can be utilized for model tuning. 

### 4.3. Techniques
- use pre-trained language model
- tune it with labeled data

### 4.4. Experimentation & Validation
- manual experimentation & validation by research analysts

### 4.5. Human-in-the-loop
- research analysts is responsible for experimentation & validation

## 5. Implementation

### 5.1. High-level design
![HLA](./assets/NER-SA-ml.png)

### 5.2. Infra
- cloud-based deployment.
- cloud agnostic deployment - nice to have
- kubernetes based deployment - nice to have
- initial setup: AWS

### 5.3. Performance (Throughput, Latency)
- for a given end-user the API response time should be acceptable: <3s
- number of concurrent users: 1-10
- number of news feeds: 1-10 
- number of RL/ML model: 1
- number of full-training loops: 0
- number of tuning-training loops and evaluations: 1-100
- number of RL/ML model deployment: 1..n

### 5.4. Security
- public access - no security
- public data - no or limited security
- public APIs - no security

### 5.5. Data privacy
- public data
- public pre-trained models
- tuned model is assumed as research project. So it is considered as public data as well

### 5.6. Monitoring & Alarms
Because of cloud agnostic deployment the following technologies are initial target
- grafana
- prometeus
- ELK (optional)

But this is yet clear how good is the given tech stack to ML Ops.

### 5.7. Cost
$300-500 per month

### 5.8. Integration points
- public News Feeds integration

### 5.9. Risks & Uncertainties
Model quality
Data accuracy
Model evaluation accuracy
Tuning time
Infra cost

## 6. Appendix

### 6.1. Alternatives
TBD: What alternatives did you consider and exclude? List pros and cons of each alternative and the rationale for your decision.

### 6.2. Experiment Results
TBD: Share any results of offline experiments that you conducted.

### 6.3. Performance benchmarks
TBD: Share any performance benchmarks you ran (e.g., throughput vs. latency vs. instance size/count).

### 6.4. Milestones & Timeline
TBD: What are the key milestones for this system and the estimated timeline?

### 6.5. Glossary
TBD: Define and link to business or technical terms.

### 6.6. References
TBD: Add references that you might have consulted for your methodology.
