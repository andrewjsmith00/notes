Bedrock Agents are a feature of [[Bedrock]] which allow you to configure [[Agents]] for your application. Agents are able to complete actions based on data and user input. This is done by orchestrating interactions between [[Foundation Model]]s, data sources, software applications and user conversations. 

Agents are able to call APIs via [[Lambda]].

## Components
The components of a Bedrock Agent are:
- Foundation Model - The Foundation Model which is invoked to interpret user input and subsequent prompts. It is also invoked to generate responses and the follow up steps
- Instructions - You write instructions that define what the agent is designed to do.
- Action groups - The actions the agent can call
- [[Bedrock Knowledge Bases]] - Knowledge bases that can be queried for extra context
- [[Bedrock Agent Prompt Templates]] - The basis for creating prompts to be sent to the model for runtime


## What happens at runtime
When the agent is invoked, the following happens:
1. The preprocessing prompt contextualises and categorises user input alongside validating input
2. The orchestration prompt then interprets the user input, invokes action groups and queries knowledge bases. This is then used as output to the user or as input to continued orchestration. The orchestration step acts as below:
	1. The agent interprets the input and generates a rationale that lays out the logic for the next step
	2. The agent predicts which action in an action group it should use or which knowledge base should be queried
	3. If the agent chooses to invoke the action, it sends the parameters that are derived from the user prompt to the [[Lambda]] configured for the action group. If there isn’t enough information, Bedrock might query a knowledge base or prompt the user for more information
	4. The agent then generates an output from invoking the action or summarising results. This observation is used to augment the base prompt. The agent will then determine if it needs to reiterate the observation process
	5. This loop will continue until the agent has an answer to the user or requires more information.
3. If a post processing template is configured, then the agent will format the response. This is off by default

These steps can be modified based on the [[Bedrock Agent Prompt Templates]].