Docker Compose Odoo 14
===

To allow VSCode to run inside the container, you need to have Python setup inside the container (after start VSCode in container, go to extension and find Python). After that, you need to setup `launch.json` as follows

```
{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "Python: Odoo",
            "type": "python",
            "request": "launch",
            "stopOnEntry": false,
            "python": "/usr/bin/python3",
            "program": "/usr/bin/odoo",
            "args": [
                "--db_host=db",
                "--db_port=5432",
                "--db_password=odoo",
            ],
            "cwd": "${workspaceFolder}",
            "console": "integratedTerminal",
        }
    ]
}
```

After that, just run the container from the debug menu and happy coding!