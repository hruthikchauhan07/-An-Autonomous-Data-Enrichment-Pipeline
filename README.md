# n8n Workflow: Reddit Post AI Classifier & Google Sheets Logger

This project is an [n8n](https://n8n.io/) workflow that automatically fetches posts from a specified subreddit, uses a Large Language Model (LLM) to classify them, and saves the categorized data to a Google Sheet.

This workflow is designed to find relevant discussions, categorize them based on their content, and store them in a structured format for easy review.

## 🚀 Features

* **Automated Fetching:** Searches a specific subreddit (e.g., `r/MachineLearning`) for posts matching a keyword.
* **Smart Filtering:** Filters posts based on criteria like minimum upvotes and whether the post has a text body.
* **AI-Powered Classification:** Uses the Google Gemini model via the LangChain `AI Agent` node to analyze the post's title and body.
* **Dynamic Categorization:** Classifies each post into predefined categories (e.g., "Beginner Question," "Technical Help," "Career/Education Advice") and generates a one-sentence summary.
* **Google Sheets Integration:** Appends the post's title, URL, upvotes, the original post body, and the AI-generated category/summary as a new row in a Google Sheet.

## 🛠️ Prerequisites

To run this workflow, you will need to set up credentials in your n8n instance for the following services:

1.  **Reddit (OAuth2):** Required for the `Search for a post` node to fetch posts from a subreddit.
2.  **Google Gemini (API Key):** Required for the `Google Gemini Chat Model` node, which powers the `AI Agent`.
3.  **Google Sheets (OAuth2):** Required for the `Append row in sheet` node to write data to your spreadsheet.

## ⚙️ Setup Instructions

1.  **Import the Workflow:**
    * Download the `My workflow.json` file from this repository.
    * In your n8n instance, create a new workflow and import this JSON file.

2.  **Configure Credentials:**
    * Navigate to the **Credentials** section in your n8n settings.
    * Add your personal credentials for **Reddit**, **Google Gemini**, and **Google Sheets**.
    * Open the imported workflow.

3.  **Connect Nodes to Credentials:**
    * **Search for a post (Reddit node):** Select your Reddit credential from the "Credential to connect with" dropdown.
    * **Google Gemini Chat Model (Gemini node):** Select your Google Gemini credential.
    * **Append row in sheet (Google Sheets node):** Select your Google Sheets credential.

4.  **Customize Workflow (Optional):**
    * **`Search for a post`:** Change the **Subreddit** and **Keyword** parameters to match your interests.
    * **`If`:** Adjust the filtering conditions (e.g., change the number of upvotes).
    * **`AI Agent`:** Modify the prompt to change the categories or the classification logic.
    * **`Append row in sheet`:** Select your own Google Sheet and update the **Sheet Name** and **Columns** to match your file.

5.  **Activate Workflow:**
    * Save the workflow.
    * Click the "Active" toggle in the top-right corner to run it on a schedule (if a schedule trigger is added) or run it manually using the "Execute workflow" button.

## 📸 Screenshots

### Workflow Canvas

Here is an overview of the complete n8n workflow graph.

![Workflow Canvas](<path/to/your/workflow_canvas_screenshot.png>)
*(Image based on:)*

### Process & Configuration

Screenshots showing the configuration of key nodes in the workflow.

| Node | Configuration |
| :--- | :--- |
| **Search for a post** | ![Reddit Node Config](<path/to/your/reddit_search_config.png>) *(Image based on:)* |
| **If Filter** | ![If Node Config](<path/to/your/if_filter_config.png>) *(Image based on:)* |
| **AI Agent Prompt** | ![AI Agent Prompt](<path/to/your/ai_agent_prompt.png>) *(Image based on:)* |
| **Google Sheets Output**| ![Google Sheets Config](<path/to/your/google_sheets_config.png>) *(Image based on:)* |

### Final Result

The output of the workflow, showing the structured data appended to the target Google Sheet.

![Google Sheets Result](<path/to/your/google_sheets_result.png>)
*(Image based on:)*
