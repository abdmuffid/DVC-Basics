# Data Version Control

## Task Description

Practice setting up and storing data using DVC on GitHub. The aim is to see how DVC makes data management easier, improving reproducibility and scalability in machine learning workflows.

## Getting Started

To get started with practicing DVC, follow these simple steps.

### Prerequisites

Before practicing DVC, please ensure you have the following prerequisites installed:

1. **Python:**
    - For Windows OS
        ```
        python --version 
        ```
    - For Unix Based OS (Linux, MacOS, etc)
        ```
        python3 --version 
        ```
    > Note: If Python is not installed, download it [here](https://www.python.org/downloads/).

2. **Git:**
    ```
    git --version 
    ```
    > Note: If Git is not installed, download it [here](https://git-scm.com/downloads).

3. **DVC:**
  	```
    dvc --version 
    ```
  	> Note: If DVC is not installed, install it using the command `pip install dvc`.

### Tutorial

1. **Open terminal or command prompt.**

2. **Set global user configuration for Git:**
    ```
    git config --global user.name "yourname"
    git config --global user.email "youremail@gmail.com"
    ```

3. **Create a Python virtual environment:**
    ```
    python -m venv env
    ```

4. **Activate the Python environment:**
    - For Windows OS
      ```
      env\Scripts\activate
      ```
    - For Unix Based OS (Linux, MacOS, etc)
      ```
      source env/bin/activate
      ```

5. **Initialize the project:**

    - Initialize a Git repository.
      ```
      git init
      ```

    - Initialize DVC inside the Git repository.
      ```
      dvc init
      ```

    - Check repository status.
      ```
      git status
      ```

    - Commit DVC initialization.
      ```
      git commit -m "Initialize DVC"
      ```

6. **Tracking Data:**

    - Create a folder for data.
      ```
      mkdir data
      ```

    - Download sample data from Dataset Registry.
      ```
      dvc get https://github.com/iterative/dataset-registry get-started/data.xml -o data/data.xml
      ```

    - Add data to DVC tracking.
      ```
      dvc add data/data.xml
      ```

    - Add "data.xml.dvc" and ".gitignore" to Git repository.
      ```
      git add "data\data.xml.dvc" "data\.gitignore"
      git commit -m "Add raw data"
      ```

    - Doubling the size of the data.
      ```
      copy data/data.xml tmp/data.xml
      cat tmp/data.xml >> data/data.xml
      ```
      > Note: First, create the tmp folder using the command `mkdir tmp`.

    - View Git log in one-line format.
      ```
      git log --oneline
      ```

    - Revert to the previous data version.
      ```
      git checkout HEAD^1 data/data.xml.dvc
      dvc checkout
      git commit data/data.xml.dvc -m “Revert dataset updates”
      ```
      > Note: Use `dvc checkout` to ensure your data files match the state they were in at the previous commit.

7. **Git remote repository:**

    - Create a new repository on GitHub.

    - Push the local repository to the Git repository.
      ```
      git remote add origin https://github.com/abdmuffid/DVC-Basics.git
      git branch -M main
      git push -u origin main
      ```

8. **Retrieve or utilize your own dataset:**

    Follow the provided tutorial to manage your dataset effectively.
