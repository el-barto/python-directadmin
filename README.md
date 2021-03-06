# Python Directadmin

*A python implementation of Directadmin's Web API*

## Introduction
The aim of this project is to provide a simple and clean implementation of Directadmin's Web API for Python developers.

[Directadmin](http://www.directadmin.com) is a popular web control panel. It provides an HTTP API which python-directadmin intends to implement, to help python developers interact with the control panel.

## Install 

Since version 0.3 python-directadmin comes with an installer script which uses [distutils](http://docs.python.org/distutils/). 

To install, just run:

```
python setup.py install
```

## Examples 

### List all users
```
import directadmin

api = directadmin.Api("admin", "password", "hostname.com", 2222)
print api.list_all_users()
```

### Connect using HTTPS and list all users
```
import directadmin

api = directadmin.Api("admin", \
                      "password", \
                      "hostname.com", \
                      2222, \
                      True)
print api.list_all_users()
```

### Create an EndUser (regular user)
```
import directadmin

api = directadmin.Api("admin", "password", "hostname.com")
user = EndUser('username', \
               'email@domain.com', \
               'userpassword', \
               'domain.com', \
               'service_package_1', \
               '1.2.3.4')
if api.create_user(user, True):
    print "User %s successfuly created" % user['username']
else:
    print "Failed to create user"
```

## Scripts 

Within the source code of this project you will find some sample scripts meant to explain how to use the API while performing some basic administrative tasks.

Check out the [Suspension Script](https://github.com/el-barto/python-directadmin/wiki/Suspension-Script) with its [source code](https://github.com/el-barto/python-directadmin/blob/master/scripts/da_suspension) and the [DirectAdmin Console](https://github.com/el-barto/python-directadmin/wiki/DirectAdmin-Console) with its [source code](https://github.com/el-barto/python-directadmin/blob/master/scripts/da_console).

## License information 

The author of this code has no relationship with Directadmin or its creators. This is just an implementation of a public API distributed under GPL v.3 license. It is meant to be used to interact with Directadmin Web Control Panel, which is a privative software that requires the purchase of a license to operate.

Copyright (C) 2009, Andrés Gattinoni

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.
