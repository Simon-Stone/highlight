[![build](https://github.com/crvernon/highlight/actions/workflows/build.yml/badge.svg)](https://github.com/crvernon/highlight/actions/workflows/build.yml)
[![DOI](https://zenodo.org/badge/632456925.svg)](https://zenodo.org/doi/10.5281/zenodo.13750915)


## highlight

#### Generate publication highlights using AI

### Installation

#### Clone this repository
Navigate to the directory you want to store this repo in and run:

```bash
git clone https://github.com/crvernon/highlight.git
```

To install this Python package in a virtual environment, you can use either pip or Anaconda.

#### Using pip

1. Create a virtual environment:
    ```bash
    python -m venv highlight_env
    ```

2. Activate the virtual environment:
    - On Windows:
        ```bash
        highlight_env\Scripts\activate
        ```
    - On macOS and Linux:
        ```bash
        source highlight_env/bin/activate
        ```

3. Install the package from the cloned `highlight` directory:
    ```bash
    pip install .
    ```

#### Using Anaconda

1. Create a virtual environment:
    ```bash
    conda create --name highlight_env python=3.11
    ```

2. Activate the virtual environment:
    ```bash
    conda activate highlight_env
    ```

3. Install the package from the cloned `highlight` directory:
    ```bash
    pip install .
    ```

### Configuring the LLMs
You can configure a variety of LLMs, both remote and local, to choose from in the app. To do this, edit the file `config.toml` in the root of this repo.

#### Setting Up API Keys
If any of the configured models require an API key, you need to set them up as Streamlit secrets.

First, you have to acquire the API key from the provider of your choice (e.g., [OpenAI](https://platform.openai.com/api-keys), [Anthropic](https://console.anthropic.com/settings/keys), or [Dartmouth](https://developer.dartmouth.edu/keys)).

Then, create a folder named `.streamlit` in the root of this repo. Inside that folder, create a file named `secrets.toml`.

Finally, store your API key(s) in the following format:

```toml
KEY_NAME = "your_api_key_here"
```

Replace `KEY_NAME` with the variable name corresponding to your provider:

| Provider    | Variable name       |
| --------    | -------             |
| Anthropic   | `ANTHROPIC_API_KEY` |
| Dartmouth   | `DARTMOUTH_API_KEY` |
| OpenAI      | `OPENAI_API_KEY`    |


Replace `your_api_key_here` with your actual API key.

#### Installing Optional Dependencies
As of right now, only the OpenAI model dependencies are automatically installed with `pip install .` If you want to use another model, you will need to install the corresponding optional dependency. For example, to use the Dartmouth model, you can use the command:
```bash
pip install ".[dartmouth]"
```

### Running the App

To run the app using Streamlit, follow these steps:

1. Follow the installation steps and ensure your virtual environment is activated.

2. Run the Streamlit app from the `highlight` directory:
    ```bash
    streamlit run app.py
    ```
