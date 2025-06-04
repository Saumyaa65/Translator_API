# Simple Translator API with Flask

This project implements a basic **Translator API** using the **Flask framework**, serving word definitions from a local dictionary dataset. It's a straightforward example of how to build a RESTful API to query information from a CSV file.

## Overview

The "Simple Translator API" provides a quick way to retrieve the definition of a specific word. By setting up a local server, you can query words through a simple API endpoint and receive their definitions, making it useful for small dictionary applications, learning about API development, or integrating into other projects.

## Features

* **Home Page (`/`):** Serves a basic HTML page (expected to be `home.html`) that could provide instructions or a simple interface for searching words.
* **Word Definition Endpoint (`/api/v1/<word>`):** Allows users to get the definition of a specific word by passing the word in the URL.
* **Data from Local CSV:** Reads word-definition pairs from a `dictionary.csv` file.
* **JSON Response:** Returns the word and its corresponding definition in a clean JSON format.

## Technologies Used

* Python
* Flask (for building the web API)
* Pandas (for efficient data reading and querying from CSV)

## How It Works

The Flask application sets up two main routes:

1.  **Home Page (`/`):**
    * When a user accesses the root URL, the `home()` function is triggered.
    * It renders an HTML template named `home.html`. You would need to create this file inside a `templates/` directory in your project structure. This `home.html` could contain a form for users to input words or simply provide instructions on how to use the API.

2.  **Word Definition Endpoint (`/api/v1/<word>`):**
    * This endpoint takes a `word` as a parameter from the URL.
    * It reads the `dictionary.csv` file into a Pandas DataFrame.
    * It then queries the DataFrame to find the `definition` corresponding to the provided `word`.
    * The definition is extracted, and the API returns a JSON object containing the `word` and its `definition`. If the word is not found, the `definition` might be an empty series or `NaN`.
