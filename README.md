# Jupyter Notebooks to Anki Cards Converter

This repository contains a Python script that processes multiple Jupyter Notebook (`.ipynb`) files, extracts the content, and generates corresponding CSV files for Anki cards. Each card's front contains a description, and the back contains the code and its output.

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Example](#example)
- [Contributing](#contributing)
- [License](#license)

## Introduction

When studying data science or programming, it's common to use Jupyter Notebooks to experiment and document your work. This tool helps you convert those notebooks into Anki cards, enabling you to use spaced repetition to memorize important concepts and code snippets.

## Features

- Batch process multiple Jupyter Notebook files.
- Extract markdown descriptions and code cells with their outputs.
- Generate Anki-compatible CSV files with card fronts and backs.
- Easy to customize and extend.

## Installation

To use this script, you need Python installed on your machine. You also need to install the required Python packages.

1. Clone the repository:

    ```sh
    git clone https://github.com/yourusername/jupyter-to-anki.git
    cd jupyter-to-anki
    ```

2. Install the required Python packages:

    ```sh
    pip install pandas nbformat
    ```

## Usage

1. Place your Jupyter Notebook files in a directory.

2. Open the `notebooks_to_anki.ipynb` file in Jupyter Notebook or Jupyter Lab.

3. Modify the `directory_path` variable to point to the directory containing your `.ipynb` files.

    ```python
    directory_path = 'path/to/your/notebooks'  # Replace with your directory path
    ```

4. Run all cells in the notebook. This will process each `.ipynb` file in the specified directory and generate a corresponding CSV file for Anki cards.

## Example

Here's an example of how the notebook works:

1. The script reads each `.ipynb` file in the specified directory.
2. It extracts markdown cells as the front content of Anki cards.
3. It extracts code cells and their outputs as the back content of Anki cards.
4. It saves the extracted content to a CSV file named after the original notebook file with `_anki_cards` appended.

```python
# Specify the directory containing Jupyter Notebooks
directory_path = 'path/to/your/notebooks'  # Replace with your directory path

# Iterate through all .ipynb files in the directory
for filename in os.listdir(directory_path):
    if filename.endswith('.ipynb'):
        notebook_path = os.path.join(directory_path, filename)
        process_notebook(notebook_path)

