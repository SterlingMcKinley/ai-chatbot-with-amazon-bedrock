# AI CHATBOT with AMAZON BEDROCK

In this project I built an AI-powered chatbot that uses Amazon Bedrock's Converse API to chat with the Amazon Nova 2 Lite foundation model, maintaining conversation history across multiple messages. Added a custom system prompt to give the chatbot a specific personality. Tune inference parameters like temperature, top_p, and max_tokens to control AI responses. Lastly, created a Bedrock Guardrail with content filtering for responsible AI.

Tools used:
- Linux
- Python
- Boto3
- Amazon Bedrock
- AWS CloudShell
- Bedrock Converse API
- BedrockGuardrails

# SYSTEM DIAGRAM

<img width="632" height="458" alt="ai-chatbot-with-amazon-bedrock_" src="https://github.com/user-attachments/assets/13525f7e-75ef-4bbc-9629-7fe39822bd2e" />
<br> </br>

To complete this project:

1. Started AWS CloudShell

2. Created a chatbot in Python using Boto3 library/module. There are a few components of the Python Script that are vital to the chat bot.
   - Within the Python script I will utilized a Converse API which is Amazon Bedrock's interface in order to talk to any model. In this project, I chose to utilize Amazon Nova Lite 2.
   - To ensure an interactive chatbot with conversation memory, custom personality and tunable response controls. Conversation history matters because it allows the model to maintain context across turns, preserve the state of a task, and support techniques like few‑shot prompting and prompt chaining. Without history, each message would be interpreted independently, making complex multi‑step interactions impossible.
   - system_prompt that shapes how the AI responds. It gets passed to every API call but never appears in the conversation itself.
   - input or messages appened to an empty list that will store the full conversation history. Each time the chatbot sends a message, it gets appended to the CLI.
   - inferenceConfig which controls how the Amazon Nova Lite 2 (model) generates responses. Here are parameters defined in my script: Temperature (Controls creativity), Top P (Controls diversity by filtering words), and Max Tokens (the max length of the response)
   - a conversation loop

3. Created a guardrail to configure content filters and sensitive information detectors in the AWS console.

4. Modified the python script by adding guardrailConfig. The guardrail ID is REQUIRED from the AWS console
   -guardrailVersion is set to "DRAFT" because the guardrail has not been published yet.

<img width="1482" height="727" alt="Chatbot_Multi-turn_conversation" src="https://github.com/user-attachments/assets/33226b95-6bf3-4f75-a9c4-0eb9187aa120" />

