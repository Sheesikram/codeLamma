# LangChain Demo with LLAMA Code Model

This project demonstrates the integration of **LangChain** with the **LLAMA model** (via Ollama) to build a code-generation assistant. The application helps developers by generating code based on user queries, using the **Codellama** model, designed for coding-related queries.

The app is built using **Streamlit** for the user interface and integrates the **LangChain framework** for processing and interacting with the LLAMA model to generate relevant code snippets.

## Table of Contents
- [Project Overview](#project-overview)
- [Requirements](#requirements)
- [Setup](#setup)
- [Usage](#usage)
- [Code Overview](#code-overview)
- [License](#license)

## Project Overview

This project leverages:
- **LangChain**: A framework to create applications powered by large language models (LLMs).
- **Ollama API**: A platform to access various LLMs, including **Codellama** for generating coding-related responses.
- **Streamlit**: A framework for building interactive web applications.
- **dotenv**: A Python library to load environment variables from a `.env` file.

The app allows users to input coding-related questions or requests, which are then processed by the **Codellama** model to generate code responses.

## Requirements

Before running the project, you need to install the following Python libraries:

- `langchain`
- `langchain-ollama`
- `streamlit`
- `python-dotenv`

You can install them using `pip`:

```bash
pip install langchain langchain-ollama streamlit python-dotenv
```

## Setup

### 1. Clone the Repository

Clone the project repository to your local machine:

```bash
git clone https://github.com/your-username/Updated-Langchain.git
cd Updated-Langchain
```

### 2. Install Dependencies

Install the required Python libraries using `pip`:

```bash
pip install langchain langchain-ollama streamlit python-dotenv
```

### 3. Set up Environment Variables

Create a `.env` file in the root directory of your project, and add the following content:

```env
LANGCHAIN_API_KEY=your_api_key_here
```

Replace `your_api_key_here` with your actual LangChain API key. If you don’t have one, you can obtain it from [LangChain's website](https://langchain.com/).

## Usage

To run the app, use the following command:

```bash
streamlit run your_script_name.py
```

This will start a local server and provide a URL, typically `http://localhost:8501`, where you can view the application.

Once the app is up and running, you can:

1. Open the app in your browser.
2. Enter a coding query or topic into the input field.
3. Press **Enter**, and the app will generate and display the corresponding code snippet or solution.

### Example Queries:
- "How to create a simple Python function?"
- "Write a loop to print numbers from 1 to 10."
- "Create a REST API using Flask."

The app will use the **Codellama** model to generate relevant code based on your input.

## Code Overview

### 1. **LangChain Setup**

- **Environment Variables**: The code uses `dotenv` to load environment variables, including the LangChain API key.
- **LangChain Tracing**: The `LANGCHAIN_TRACING_V2` environment variable is set to `true` for debugging purposes.
- **Prompt Template**: The `ChatPromptTemplate` is used to define the conversation structure, where the system message defines the assistant's role as a coder, and the user message expects a code-related response.

### 2. **Streamlit Framework**

The app uses Streamlit to:
- Display a title on the web page.
- Provide an input field for the user to type their question or request related to code.
- Display the generated response (code) once the user submits their query.

### 3. **Ollama and Codellama Model**

- **Ollama**: The `Ollama` class is used to interface with the Codellama model, which specializes in generating code-related responses.
- **StrOutputParser**: The `StrOutputParser` is used to parse the model’s response, ensuring that the output is in a readable and clean format for display.
- **Prompt Pipeline**: The prompt is processed through the LangChain pipeline, which connects the input (question) to the model and then parses the result for output.

### 4. **Interactive Q&A**

Once the user provides a coding-related question via the Streamlit interface, the app processes it using LangChain and the Codellama model, and the result is displayed dynamically on the Streamlit app.

## License

This project is open-source and available under the [MIT License](LICENSE).
