Docker Compose Odoo 14
===

## Start Odoo instance with docker

To start an Odoo instance, please perform the following steps:

1. Pull this repo
2. Pull enterprise addons
3. Configure the path to enterprise addons
4. Run `docker-compose up`
5. Run `chmod 777 -R etc` to grant permissions
6. Restart odoo using `docker-compose restart odoo14` (replace `odoo14` with the service name)
7. Happy coding!

If logfile is enabled in `odoo.conf`, use this command to print the log (adapt the path to log file accordingly)

```
tail -fn 500 etc/odoo-server.log
```

## Start Odoo when running VSCode inside container

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
