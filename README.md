## What is Systemd?

- It is basically a "init System". "Init System" is a type of process. It is the most important process running on your server. For that reason, it is also referred to as PID1 short for process ID 1.
- The Job of the process is to manage all other processes. When you start a process in a linux such as an Apache in the case of web server, the request to start the process is first sent to the init system which then starts it up. When you stop a process, reload a process, and restart a process, the init system is what does all of that for you.

## Working with Units:

- Units in Systemd ae resources that it is able to manage.
- These include services, timers, mounts, automounts and there's more

To put it in another way, Units are things that systemd can manager for you and service is a type of unit.

```bash
sudo systemctl restart apach2
```

it is useful if you have changed the configuration file.

## What is service file?

Service files are just text files that contain instructions tha tell systemd how it needs to manage that particular service.

## System Unit Directories

1- /etc/systemd/system (High Priority)
2- /run/systemd/system (Then Higher Priority)
3- /lib/systemd/system (Then Higher Priority)

Any service file or configuration that is stored in a directory of high priority is going to take priority. That means that any service files or configurations that you might have in the /run/systemd/system directory, those are going to take priority over /lib/systemd/system.

```bash
sudo systemctl daemon-reload
```

```bash
m h  dom mon dow   command
# Run this command at 5 minute of every hour e.g 1:05, 2:05, 3:05, 4:05, 5:05 ect
5 * * * * echo "Hello World"
# Run this command every day at 9:05 am
5 9 * * * echo "Hello World"
# Run this command on the 15th day of every month at 9:05 am
5 9 15 * * echo "Hello World"

@hourly echo "Hello World"

@reboot echo "Hello World"
```

https://crontab-generator.org/
