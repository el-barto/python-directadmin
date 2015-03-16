# Introduction #

One of the sample scripts included in the source of python-directadmin is called da\_console. This little script provides an interactive console to interact with a Directadmin Server.

Currently the commands available within this console are very few. In the future some more could be added, and the console itself could be refined.

# Details #

## Commands ##

The current commands available in the console are:

  * `connect`                - Connect to a Directadmin Server
  * `config_file`            - Shows the configuration file in use
  * `help | ?`               - Print command information
  * `list`                   - Prints the list of users of a certain type (users/resellers/admins)
  * `quit | Ctrl+C | Ctrl+D` - Quit the console
  * `server_info`            - Prints statistical information about the server
  * `show_servers`           - Shows all the configured servers
  * `suspend`                - Suspends a user on Directadmin
  * `unsuspend`              - Un-suspends a user on Directadmin
  * `version`                - Print version information

**New**: now the suspend, unsuspend and list commands come with auto-complete. If you are connected to a server, you can use tab i.e. to complete the username to suspend!

## Parameters ##

The script also accepts the following parameters when invoked.

  * `--version`              - Prints version information and quits
  * `-h, --help`             - Prints help information and quits
  * `-c FILE, --config=FILE` - Use FILE as configuration file

## Configuration file ##

The configuration file is a simple .ini file. You can define different servers (with connection and login information) by defining different sections of the file like this:

```
[server1]
hostname = server1.domain.com
port = 9999
username = admin
password = admin123

[server2]
hostname = server2.domain.com
username = admin
password = admin123
https = True
```

### Using a configuration file ###

**Default**

By default DAConsole looks for the file `~/.daconsole.conf` (this is a file called ".daconsole.conf" located on the user's home folder).

**Defining a new configuration file**

You can use de `-c` or `--config` command line parameter to define a specific configuration file location. For example:

```
da_console -c /etc/daconsole.conf
```

**Changing the default configuration file**

If you want to change the default location for the configuration file, you can change the value of the variable `__config__` which is near the top of the daconsole.py file (under `__revision__`). For example:

```
__config__ = '/etc/daconsole.conf'
```

# To-Do #

  * Implement more API commands
  * ~~The `connect` command currently works only on interactive mode, you call it and it asks you for the connection information. The user should be able to pass that information as a parameter of the command.~~
  * ~~Connection information could also be defined at a configuration file~~
  * ~~The console should be able to handle more than one host, so that a single console running on one box could monitor many different servers~~