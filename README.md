# nautobot_docker_dev_env
Nautobot development environment with Docker Compose.

1. Install invoke. This is a python based cli tool for abstracting tasks.
```
https://www.pyinvoke.org/installing.html
```

2. Install poetry. This is a python virtual environment/package manager.
```
https://python-poetry.org/docs/#installing-with-the-official-installer
```

3. Install cookiecutter, bake the cookie. You can accept the prompt defaults without modifying the values for now.
```
https://github.com/nautobot/cookiecutter-nautobot-app/blob/develop/README.md
```

4. Change into the created cookie directory

5. Activate python virtual environment
```
poetry shell
```

7. Install Nautobot related packages (see pyproject.toml)
```
poetry install
```

7. Create default credential environment variables
```
cp development/creds.example.env development/creds.env
```

9. Builds Nautobot application containers
```
invoke build
```

11. Starts DB, runs migrations
```
invoke makemigrations
```

10. Starts all Nautobot containers and follows their logs. After a few minutes, you should see a Nautobot Initialized log
```
invoke debug
```

12. In a browser:
```
http://localhost:8080
```

14. Creds: admin/admin
