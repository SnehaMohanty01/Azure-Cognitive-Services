Language Detection with Azure Text Analytics

This repository contains two Python scripts (rest-client.py and sdk-client.py) for detecting the language of text input using Azure's Text Analytics API. The scripts provide different methods of interacting with the API: one using REST API calls and the other using the Azure SDK. Both methods require an .env file to securely store the Azure service credentials.

Features
REST API Client (rest-client.py): Directly calls the Azure Text Analytics REST API for language detection.
SDK Client (sdk-client.py): Uses the Azure SDK to interact with the Text Analytics API, simplifying the code and handling authentication more easily.
Prerequisites

Azure Subscription: You'll need an Azure account and a Text Analytics resource. Set up an Azure account if you don't have one.
Azure Text Analytics API Key and Endpoint: After creating your Text Analytics resource on Azure, you'll have access to an API key and endpoint URL.
Python 3.7 or higher: Install Python if necessary.
Python Packages: Install required packages as described below.

Setup Instructions

Step 1: Clone the Repository
bash

Copy code
git clone https://github.com/your-username/your-repository-name.git
cd your-repository-name

Step 2: Install Required Packages
Install the required packages with:

bash
Copy code
pip install -r requirements.txt
requirements.txt should include:

Copy code
python-dotenv
azure-ai-textanalytics

Step 3: Set Up .env File
Create a .env file in the root directory of the project.
Add your Azure Text Analytics endpoint and key as shown below:
plaintext

Copy code
AI_SERVICE_ENDPOINT='https://your-resource-name.cognitiveservices.azure.com/'
AI_SERVICE_KEY='your-api-key'

Step 4: Run the Scripts
You can use either the rest-client.py or sdk-client.py script to detect the language of your text input.

Usage
Using rest-client.py
Run the script:

bash
Copy code
python rest-client.py
Enter a text string when prompted to detect its language. Type "quit" to stop the script.

Using sdk-client.py
Run the script:

bash
Copy code
python sdk-client.py
Enter a text string when prompted to detect its language. Type "quit" to stop the script.

Example Output
For either script, you’ll see output like this:

plaintext
Copy code
Enter some text ("quit" to stop)
Hello, how are you?

Language: English

Code Overview

rest-client.py
Load Environment Variables: Loads the API key and endpoint from the .env file.
User Input Loop: Continuously accepts user text input until "quit" is entered.
HTTP Request: Makes a POST request to Azure’s Text Analytics language detection endpoint with the text input.
Response Handling: Parses and prints the detected language if successful, or outputs an error message if something goes wrong.

sdk-client.py
Load Environment Variables: Loads the API key and endpoint from the .env file.
Azure Client Initialization: Creates a TextAnalyticsClient instance using Azure's SDK.
Language Detection: Calls the detect_language method from the SDK, which simplifies the API call process.
Response Handling: Outputs the detected language or an error message if the call fails.
Error Handling
Both scripts include basic error handling to manage:

Invalid API Credentials: Ensures the API key and endpoint are correctly loaded from the .env file.
Connection Errors: Prints an error message if there’s an issue connecting to Azure.
API Errors: Handles unexpected API responses or errors.

Best Practices
Secure your API key: Never hard-code API keys in your code. Always store them in a secure location like an .env file.
Limit Requests: Be mindful of API request limits to avoid excessive charges or throttling by Azure.

License
This project is licensed under the MIT License. See the LICENSE file for details.

