# Python 3 & PostgreSQL

## Summary

*Develop applications with Python 3 and PostgreSQL. Includes a Python application container and PostgreSQL server, and a Django test project.*

| Metadata | Value |  
|----------|-------|
| *Contributors* | The [VS Code Python extension](https://marketplace.visualstudio.com/itemdetails?itemName=ms-python.python) team |
| *Definition type* | Dockerfile |
| *Languages, platforms* | Python |

## Using this definition with an existing folder

First, for convenience, this definition will automatically install dependencies from your `requirements.txt` file when the container is built. However, note that `requirements.txt` in the root of this definition folder is **only present for testing** and is not used or required by the definition itself.

Second, only the integrated terminal is supported by the Remote - Containers extension. You may need to modify `launch.json` configurations to include the following value if an external console is used.

```json
"console": "integratedTerminal"
```

Beyond that, just follow these steps:

1. If this is your first time using a development container, please follow the [getting started steps](https://aka.ms/vscode-remote/containers/getting-started) to set up your machine.

2. To use VS Code's copy of this definition:
   1. Start VS Code and open your project folder.
   2. Press <kbd>F1</kbd> select and **Remote-Containers: Add Development Container Configuration Files...** from the command palette.
   3. Select the Python 3 & PostgreSQL definition.

3. To use latest-and-greatest copy of this definition from the repository:
   1. Clone this repository.
   2. Copy the contents of `containers/python-3-postgres/.devcontainer` to the root of your project folder.
   3. Start VS Code and open your project folder.

4. After following step 2 or 3, the *only* the contents of the `.devcontainer` folder in your project can be adapted to meet your needs. Ignore other files and folders.

5. Finally, press <kbd>F1</kbd> and run **Remote-Containers: Reopen Folder in Container** to start using the definition.

## Testing the definition

This definition includes some test code that will help you verify it is working as expected on your system. Follow these steps:

1. If this is your first time using a development container, please follow the [getting started steps](https://aka.ms/vscode-remote/containers/getting-started) to set up your machine.
2. Clone this repository.
3. Start VS Code, press <kbd>F1</kbd>, and select **Remote-Containers: Open Folder in Container...**
4. Select the `containers/python-3-postgres` folder.
5. After the folder has opened in the container, use <kbd>ctrl</kbd>+<kbd>shift</kbd>+<kbd>`</kbd> to open a terminal and run the following commands to initialize the database and create a super user:
    ```bash
    cd test-project
    python manage.py migrate
    python manage.py createsuperuser
    ```
6. Next, press <kbd>F5</kbd> to start the project.
7. Once the project is running, press <kbd>F1</kbd> and select **Remote-Containers: Forward Port...**
8. Select port 5000 and click the "Open Browser" button in the notification that appears.
9. You should see a page with a message indicating the install was successful. You can also go to `http://localhost:<port>/admin` and sign in.
10. From here, you can add breakpoints or edit the contents of the `test-project` folder to do further testing.

## License

Copyright (c) Microsoft Corporation. All rights reserved.

Licensed under the MIT License. See [LICENSE](https://github.com/Microsoft/vscode-dev-containers/blob/master/LICENSE)
