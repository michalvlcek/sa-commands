Useful (symfony) commands for working with AWS.

### # installation

* `composer install`
* create `.env` file from example (`cp .env.example .env`) and setup

### # usage
* `php app.php` - for list of all commands
* `php app.php name:of:command [[option] --argument]`

### # commands

* `demo:greet Fabien` - example command
* [`ec2:hosts-info`](#ec2hosts-info) - creating `/etc/hosts` records from all EC2 instances (name and IP)

----

#### `ec2:hosts-info`

Command which allows to grab informations from all EC2 instances (across all regions) in "hosts" style format.
Default call (with no argument) prints output to stdOut. If you set `file` argument output is appended to specified file.

```sh
php app.php ec2:hosts-info # dump to std output
```
```sh
php app.php ec2:hosts-info --file=/etc/hosts # dump to file
```

results in:

```
 12.12.123.123  SomeName        # i-c12ab06c
 12.12.12.1     AnotherName     # i-05fce0883ca1d7f12
```
