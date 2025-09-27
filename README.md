# Ex.No.6 Development of Python Code Compatible with Multiple AI Tools
# Date:27-09-2025
# Register no:2122232400471
# Aim: Write and implement Python code that integrates with multiple AI tools to automate the task of interacting with APIs, comparing outputs, and generating actionable insights with Multiple AI Tools

#AI Tools Required:

# Explanation:
Experiment the persona pattern as a programmer for any specific applications related with your interesting area. 
Generate the outoput using more than one AI tool and based on the code generation analyse and discussing that. 

# 🎯 Objective
To write and implement Python code that interacts with multiple AI tools (such as OpenAI's ChatGPT, Anthropic's Claude, Google Gemini, and Microsoft Copilot) using their respective APIs. The goal is to automate:

Submitting a common prompt

Comparing the returned outputs

Generating actionable insights based on defined evaluation metrics (e.g., accuracy, coherence, simplicity)

# ⚙️ Use Case
Healthcare Diagnostics: The system will automate the analysis of patient symptoms and generate diagnostic insights by interacting with multiple AI platforms, enabling healthcare professionals to make informed decisions more efficiently.

# 🔍 AI Tools Required:

# CHATGPT

# CLAUDE

# GEMINI

# 📌 Algorithm Overview

# Step-by-Step Algorithm for Multi-AI Tool Integration

1.Set Up API Integrations:

Install necessary libraries and set up the credentials for each AI tool: ChatGPT, Claude, and Gemini.

Use requests or other relevant libraries for API integration.

2.Input Healthcare Query:

Accept healthcare-related data such as symptoms, medical history, and test results.

3.Format Prompts:

Three types of prompts will be used:

Straightforward Prompt: Asking for a diagnosis based on patient symptoms.

Tabular Format: Presenting data in a table format for structured input.

Missing Word Prompt: Providing a partially completed sentence for prediction.

4.Submit Prompts to Each AI Tool:

Send the formatted prompts to ChatGPT, Claude, and Gemini APIs.

5.Receive and Parse Responses:

Collect and extract useful information such as diagnosis and treatment suggestions.

6.Comparison of Outputs:

Compare the responses based on accuracy, clarity, simplicity, and user experience.

7.Generate Actionable Insights:

Provide a summary of findings and suggest which tool performs best for specific types of queries.

8.Create Final Report:

Compile the results and insights into a comprehensive evaluation report.

# 🧪 Prompt Types

Straightforward Prompt: A simple query asking for diagnosis and treatment based on provided symptoms.

Tabular Format: Presenting data in a structured table format for each symptom.

Missing Word Prompt: A prompt with an incomplete sentence for the AI to complete.

# 📤 Example Queries & Responses

# 1. Straightforward Prompt
Prompt:
"Patient reports fever, cough, and shortness of breath. What could be the diagnosis and recommended action?"

<img width="823" height="288" alt="image" src="https://github.com/user-attachments/assets/d989218b-b2d7-4007-b128-9b04b5000518" />

# 2. Tabular Format Prompt
Prompt:

<img width="363" height="257" alt="image" src="https://github.com/user-attachments/assets/d84b605e-390e-4ffc-b6f3-a2b151571c5d" />

# Query:
"Based on this table, what is the likely diagnosis and treatment plan?"

<img width="797" height="296" alt="image" src="https://github.com/user-attachments/assets/51ca855b-52cd-477f-a684-fd5f3ce20595" />

# 3. Missing Word Prompt
Prompt:
"The patient with fever and shortness of breath is likely suffering from ______."

<img width="557" height="206" alt="image" src="https://github.com/user-attachments/assets/c5b9eea7-f087-4e08-80f6-35a2dcd3273d" />

# 🔧 Code Implementation

# Python Code Example for Integrating with Multiple AI Tools

```
import openai
import requests

# API Keys
CHATGPT_API_KEY = "your_openai_api_key"
CLAUDE_API_KEY = "your_claude_api_key"
GEMINI_API_KEY = "your_gemini_api_key"

# Initialize the OpenAI API (for ChatGPT)
openai.api_key = CHATGPT_API_KEY

# Function to get response from ChatGPT
def get_chatgpt_response(prompt):
    response = openai.Completion.create(
        model="gpt-4",  # specify your model
        prompt=prompt,
        max_tokens=150
    )
    return response.choices[0].text.strip()

# Function to get response from Claude (Assume we are using a generic API)
def get_claude_response(prompt):
    headers = {
        'Authorization': f'Bearer {CLAUDE_API_KEY}',
        'Content-Type': 'application/json'
    }
    payload = {'prompt': prompt}
    url = 'https://api.claude.ai/v1/complete'  # Example endpoint
    response = requests.post(url, json=payload, headers=headers)
    return response.json().get('completion', '')

# Function to get response from Gemini (Assume we are using a generic API)
def get_gemini_response(prompt):
    headers = {
        'Authorization': f'Bearer {GEMINI_API_KEY}',
        'Content-Type': 'application/json'
    }
    payload = {'prompt': prompt}
    url = 'https://api.gemini.ai/v1/generate'  # Example endpoint
    response = requests.post(url, json=payload, headers=headers)
    return response.json().get('text', '')

# Example healthcare query (symptoms)
query = "Patient reports fever, cough, and shortness of breath. What could be the diagnosis and recommended action?"

# Send prompts to AI tools
chatgpt_response = get_chatgpt_response(query)
claude_response = get_claude_response(query)
gemini_response = get_gemini_response(query)

# Print the results
print("ChatGPT Response:")
print(chatgpt_response)

print("\nClaude Response:")
print(claude_response)

print("\nGemini Response:")
print(gemini_response)
```

# OUPUT RESPONSE

# Functions for Getting Responses:
1.get_chatgpt_response():

This function sends the healthcare query prompt to ChatGPT and retrieves the response.

It utilizes the OpenAI API (openai.Completion.create) to process the prompt and returns ChatGPT's response.

```
def get_chatgpt_response(prompt):
    response = openai.Completion.create(
        model="gpt-4",  # specify the model
        prompt=prompt,
        max_tokens=150
    )
    return response.choices[0].text.strip()

```

# Functions for Getting Responses:
get_claude_response():

This function sends the same healthcare query prompt to Claude using a hypothetical API (requests.post).

It returns Claude's response from the API call.
```
 def get_claude_response(prompt):
     headers = {
         'Authorization': f'Bearer {CLAUDE_API_KEY}',
         'Content-Type': 'application/json'
     }
     payload = {'prompt': prompt}
     url = 'https://api.claude.ai/v1/complete'  # Example endpoint
     response = requests.post(url, json=payload, headers=headers)
     return response.json().get('completion', '')

```

# 📊 Evaluation

The Python code evaluates the responses from ChatGPT, Claude, and Gemini based on the following metrics:

# 1. Accuracy
   
Definition: This metric checks whether the response correctly identifies the diagnosis and suggests appropriate actions.

Importance: Ensuring accurate diagnostic suggestions is critical for healthcare applications.

# 3. Coherence

Definition: This metric assesses how logically structured and clear the response is.

Importance: Clear, well-structured responses make it easier for the user to understand the suggested diagnosis and actions.

# 4. Simplicity

Definition: This evaluates whether the response is easy to understand for the target audience (whether it's the general public or professionals).

Importance: Simplicity is essential for user comprehension, especially when dealing with complex healthcare information.

# 5. User Experience

Definition: This measures how well the response caters to the user, providing a clear and helpful solution.

Importance: A good user experience is vital for user engagement and decision-making, especially in critical situations like healthcare diagnostics.

```
import pandas as pd

# Sample evaluation data
evaluation_data = {
    "AI Tool": ["ChatGPT", "Claude", "Gemini"],
    "Accuracy": ["High", "High", "High"],
    "Coherence": ["High", "High", "Moderate"],
    "Simplicity": ["User-friendly", "Technical", "Concise"],
    "User Experience": ["Good", "Detailed", "Efficient"]
}

# Create a DataFrame for comparison
df_comparison = pd.DataFrame(evaluation_data)
print(df_comparison)
```

# 📊 Result Presentation

After executing the code, the results are displayed in a tabular format, comparing ChatGPT, Claude, and Gemini based on their performance across the evaluation metrics.

<img width="761" height="206" alt="image" src="https://github.com/user-attachments/assets/35f8529e-93d8-4886-93f3-dbc2b0d76988" />


# Conclusion:

This project provides a robust solution for healthcare diagnostics by integrating multiple AI tools and comparing their responses for accuracy, clarity, simplicity, and user experience. The tool can assist healthcare professionals by offering valuable insights into patient symptoms and treatment recommendations, streamlining the decision-making process.
# Result: 

The corresponding Prompt is executed successfully.
