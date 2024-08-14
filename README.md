

# Shopping Assistant Chatbot

## Overview

The Shopping Assistant Chatbot is a Python application designed to facilitate shopping by providing information about food recipes and supermarket items. It leverages the GPT-2 model for generating natural language responses and integrates data from Excel spreadsheets to offer specific item details and recommendations.

## Features

- **Natural Language Processing:** Utilizes the GPT-2 model to understand and respond to user queries.
- **Item Information:** Retrieves and displays details about supermarket items, including price and brand.
- **Recipe Suggestions:** Provides examples of food recipes to inspire users.
- **Preference Tracking:** Remembers user preferences for shopping items to personalize future interactions.

## Requirements

To run this chatbot, you'll need:

- **Python 3.7 or higher**: Ensure Python is installed on your system.
- **Libraries**: Install required libraries using pip:
  - `pandas` for data manipulation.
  - `transformers` for GPT-2 model.

## Installation

Follow these steps to set up the chatbot:

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/yourusername/shopping-assistant-chatbot.git
   cd shopping-assistant-chatbot
   ```

2. **Install Dependencies:**
   Install the necessary Python libraries:
   ```bash
   pip install pandas transformers
   ```

3. **Prepare Data Files:**
   - Ensure you have the following Excel files:
     - `food_recipes_large.xlsx`: Contains food recipes with columns like `Food Item Name`.
     - `supermarket_items_large.xlsx`: Contains supermarket items with columns like `Item Name`, `Price`, and `Brand`.
   - Place these files in the `/content` directory or adjust the file paths in the script accordingly.

## Usage

To interact with the chatbot:

1. **Run the Chatbot Script:**
   ```bash
   python chatbot.py
   ```

2. **Provide User Input:**
   - **Show Examples:** Type `show me more food` or `show me more supermarket` to get additional examples.
   - **Find Item Details:** Enter a query like `I want to buy [item name] from Walmart` to get information about a specific item.
   - **Exit:** Type `exit`, `quit`, or `bye` to end the conversation.

## Detailed Explanation of Functions

### `generate_response(prompt)`

- **Purpose:** Generates a natural language response to the user's input using the GPT-2 model.
- **Parameters:** `prompt` (string) - The user's query or input.
- **Returns:** A string containing the generated response.

### `get_random_examples(df, num_examples=5)`

- **Purpose:** Retrieves a random sample of items from the provided DataFrame.
- **Parameters:** 
  - `df` (DataFrame) - The DataFrame to sample from (either food recipes or supermarket items).
  - `num_examples` (int) - The number of random examples to return.
- **Returns:** A DataFrame containing the sampled examples.

### `get_supermarket_info(item_name)`

- **Purpose:** Fetches details of an item from the supermarket database.
- **Parameters:** `item_name` (string) - The name of the item to search for.
- **Returns:** A list of dictionaries with item details (`Item Name`, `Price`, `Brand`) if found; otherwise, `None`.

### `remember_shopping_preference(item_name, category)`

- **Purpose:** Stores the user's preference for a particular item in a specified category.
- **Parameters:**
  - `item_name` (string) - The name of the item.
  - `category` (string) - The category of the item (e.g., 'Shopping').
- **Returns:** None. Updates the `shopping_preferences` dictionary.

### `handle_shopping_query(item_name)`

- **Purpose:** Handles queries related to purchasing items and provides information or generates additional responses if the item is not found.
- **Parameters:** `item_name` (string) - The name of the item being queried.
- **Returns:** A string with details about where to buy the item or a generated response if the item is not found.

### `initial_welcome()`

- **Purpose:** Provides a welcome message with examples of food and supermarket items.
- **Returns:** A string with the initial greeting and example items.

### `show_more_examples(df, num_examples=10)`

- **Purpose:** Shows additional examples from the provided DataFrame.
- **Parameters:**
  - `df` (DataFrame) - The DataFrame to sample from (either food recipes or supermarket items).
  - `num_examples` (int) - The number of additional examples to return.
- **Returns:** A DataFrame containing the sampled examples.

## Notes

- Ensure that the Excel files are formatted correctly with the necessary columns.
- Adjust file paths in the script if the data files are not in the `/content` directory.

