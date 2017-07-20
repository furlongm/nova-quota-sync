Nova Quota Sync
===============

What is it?
-----------
This is a small script that compares nova quota usage information with
the actual usage per resource (tenant/user).

It also provides an easy way to synchronize quotas in case of mismatch.


Usage
-----

```shell
$ python nova-quota-sync -h
usage: nova-quota-sync [-h] [-a] [-s] [-p PROJECT] [-c CONFIG] [-d]

optional arguments:
  -h, --help            show this help message and exit
  -a, --all             show the state of all quota resources
  -s, --sync            perform synchronization of mismatched resources
  -p PROJECT, --project PROJECT
                        operate only on this project ID
  -c CONFIG, --config CONFIG
                        path to nova configuration file
  -d, --debug           enable debug mode
```


Examples
--------

python nova-quota-sync --config my_nova.conf --all --sync

python nova-quota-sync --config my_nova.conf

python nova-quota-sync --all --no_sync --project "d945d5ce-cfb8-11e4-b9d6-1681e6b88ec1"


Nova versions supported
-----------------------
Tested up to Liberty


Bugs and Disclaimer
-------------------
Bugs? Oh, almost certainly.

Since it updates nova DB use it with extreme caution.
