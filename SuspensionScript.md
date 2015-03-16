## Introduction ##

The python-directadmin source includes a little script file called [da\_suspension](http://code.google.com/p/python-directadmin/source/browse/trunk/scripts/da_suspension). The main purpose of it is being a sample of the usage of the API. However it may be useful to suspend/unsuspend users from command line.


## Usage ##

```
da_suspension [options] suspend|unsuspend <username>
```

Options:
  * `--version`: show program's version number and exit
  * `-h, --help`: show this help message and exit
  * `-u USERNAME, --user=USERNAME`: Directadmin admin/reseller username
  * `-p PASSWORD, --password=PASSWORD`: Directadmin admin/reseller password
  * `-H HOSTNAME, --host=HOSTNAME`: Directadmin hostname (default: localhost)
  * `-P PORT, --port=PORT`: Directadmin port (default: 2222)

## Examples ##

Suspend the user "baduser" at mydirectadminserver.com host. In this case we will be prompted to enter admin's password.
```
da_suspension -u admin -H mydirectadminserver.com suspend baduser
```

Un-suspend the user "fineuser" at localhost. In this case we will be prompted to enter admin/reseller username and password.
```
da_suspension unsuspend fineuser
```