# mysql_password_hash
MySQL Password and Hash Generator

This Python program creates a MySQL 5 password-hash that can be used to create MySQL GRANTS using a hash instead of a password.
This is useful in many cases, including using the Puppet's Puppetlabs-MySQL module which expects a password hash when creating GRANTs

# For example:
```
GRANT ALL ON *.* to user@% identified by PASSWORD 'PASS-HASH';
```

The program can generate random passwords of any length and provide a hash or it can ask for a password and then output the hash.

It works both with command line arguments as well as in interactive mode.

# Usage

usage: netapp_replication_report.py [-h] [-c CONFIG] [-s HOSTNAME]
                                    [-u USERNAME] [-p PASSWORD] [-r RPO]

```
$ ./mysql_password_hash -h
usage: mysql_password_hash [-h] [-p PASSWORD | -r] [-l PASSWORD_LENGTH]

MySQL Password Hash Generator

optional arguments:
  -h, --help            show this help message and exit
  -p PASSWORD, --password PASSWORD
                        Enter a password
  -r, --generate_random
                        Generate a random password
  -l PASSWORD_LENGTH, --password_length PASSWORD

```

# Using Command line arguments - User provided password
$ mysql_password_hash -p secret
PASSWORD: secret
HASH: *14e65567abdb5135d0cfd9a70b3032c179a49ee7

# Using Command line arguments - Random password with X length (default length=12)
$ mysql_password_hash -r -l 20
PASSWORD: gnlrn96^g18jcblmssa6
HASH: *e3cbe60709e8abe2082c92cc5e72a762d5f18e22

# interactive mode (no arguments)
mysql_password_hash

