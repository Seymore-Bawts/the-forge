The Forge

This project is the manifestation of the Genesis Mandate: an effort to solve systemic problems in software development, starting with "The Babel of Tooling."

The Forge is a tool for managing ephemeral, declarative, and intelligent development environments.
Setup and Installation

This project is structured as a proper Python package. To install it for development, follow these steps.

1. Prerequisites:

    Python 3.8+

    pip

    Docker (must be running)

2. Get the Code:
Clone this repository to your local machine.

3. Create and Activate Virtual Environment:
It is highly recommended to use a virtual environment to manage dependencies.

# Navigate into the project directory
cd the-forge 

# Create the environment
python -m venv .venv

# Activate it (on macOS/Linux)
source .venv/bin/activate

# Or on Windows
# .\.venv\Scripts\activate

4. Install Dependencies:
Install all required packages from the requirements.txt file and then install the forge package itself in an editable mode. This allows you to make changes to the code and see them reflected immediately.

pip install -r requirements.txt
pip install -e .

That's it! The forge command is now available in your shell as long as the virtual environment is active.
Usage

After installation, the forge command will be available in your shell.

    Create a forge.yml file in your project directory (see example below).

    Run the commands:

    forge up
    forge status
    forge shell <service_name>
    forge down

Example forge.yml

project_name: my-web-project
services:
  - name: web
    image: python:3.10-slim
    ports:
      - "8000:8000"
    volumes:
      - ".:/app" # Mounts the current directory into /app in the container
    command: "tail -f /dev/null" # Keeps the container running for you to shell into
  - name: db
    image: redis:alpine

