# Game Bot ML Design Doc

## 1. Overview
Design, develop and deploy into Production Reinforcement Learning based Game Bot agent.       

## 2. Motivation & Success metrics
It is expected that such bots will get much better scores in game environments like https://dojorena.io/.

## 3. Requirements & Constraints
Game Bots are doing actions selection at game time. Utilizing Machine Learning should give extra information for making better decisions what action to select in given situation. It is also very interesting to get some feedback about budget and time constrains required to run such systems in production. 
At the beginning we have the following constrains:
- Game Bot response time (decision) < 1s
- Infra budget: $300-500

### 3.1 What's in-scope & out-of-scope?
Image (game screen) recognition is out of scope. We consider we could get game information in structured text format. 

## 4. Methodology

### 4.1. Problem statement
It is hard and costly to implement Reinforcement Learning only based game bot. In this project we'd like to mix human-created strategies together with Reinforcement Learning base hints or priorities which strategy to use. 

### 4.2. Data
We assume that the game consists of limited number of steps. Each step have a game state related to this step. Game history is a full set of such steps.
Set of game histories is our input data.

### 4.3. Techniques
What machine learning techniques will you use? How will you clean and prepare the data (e.g., excluding outliers) and create features?

### 4.4. Experimentation & Validation
Game Bot and related ML models will be evaluating in some online game environments. As such games are quite random - some repeatable set of experiments will be used for a given model.   

### 4.5. Human-in-the-loop
A game bot developer is expected to write and implement set of game strategies or features. Machine Learning (Reinforcement Learning) models should provide some weights or priorities which strategy or feature to use in a given game situation.

## 5. Implementation

### 5.1. High-level design
![HLA](./assets/game-bot-ml.png)

### 5.2. Infra
- cloud-based deployment.
- cloud agnostic deployment - nice to have
- kubernetes based deployment - nice to have
- initial setup: AWS

### 5.3. Non-functional requirements: Constraints, Performance (Throughput, Latency)
- game bot response latency: <1s
- number of parallel game bots: 1-100
- number of parallel game environments: 1-20 
- number of RL/ML model: 1
- number of RL/ML model deployment: 1..n
- number of training loops: limited only by time and resources 
- number of parallel training loops: 1 

### 5.4. Security
- game bot connects to a game environment with API key
- in tournament mode - it is important to have API key /connectivity to public game environment secure
- in training / simulation mode - game environment assumed to be private, not exposed to the internet and security is less important

### 5.5. Data privacy
As game events are public - game data assumed to be public data.
Trained model is assumed as research project. So it is considered as public data as well.  

### 5.6. Monitoring & Alarms
Because of cloud agnostic deployment the following technologies are initial target
- grafana
- prometeus
- ELK (optional)

But this is yet clear how good is the given tech stack to ML Ops.

### 5.7. Cost
$300-500 per month

### 5.8. Integration points
Game Environment is our main integration point. Usually this is a custom real-time JSON over Web Sockets protocol.
It is assumed that Game Environment provides sample clients in a different languages.
Data parsing and normalization is required.
Data collection and batching is required.

### 5.9. Risks & Uncertainties
Model quality
Data accuracy
Model evaluation accuracy
Training time
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
- [RL @illya13](https://illya13.github.io/RL/)
- [Coding DOJO](https://dojorena.io/)
