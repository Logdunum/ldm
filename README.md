Purpose
=======

This is the Logdunum CLI for tailing logs from your [Logdunum](https://github.com/Logdunum/logdunum) MongoDB servers

Install
=======

* add the Logdunum CLI to your system as a global :

```bash
#install the cli
$> sudo npm install -g ldm
```

Usage
=====
Please read the 

* in your console, using the ldm CLI :

```bash
$> ldm -f -n 50
```

You can get help with the cli using --help :

```bash
$> ldm --help

  Usage: ldm [options]

  Options:

    -h, --help                                                                   output usage information
    -V, --version                                                                output the version number
    -n, --lines [number]                                                         only output the last n lines
    -f, --follow                                                                 output appended lines as their arrive
    -l, --level [level]                                                          filter lines by level, either as a regexp, or a comma separated list
    -m, --min [level]                                                            minimal level threshold, [trace < debug < log < info < warn < error < fatal]
    -u, --user [user]                                                            output only what happened for user
    -c, --no-color                                                               output without colors
    -d, --rawdate                                                                output raw date, rather than humanized ones
    -p, --fullpath                                                               output full file path, rather than humanized ones
    --with-logdunum-configuration-file                                           set logdunum option [configuration file]
    --with-logdunum-host <localhost>                                             set logdunum option [host]
    --with-logdunum-port <27017>                                                 set logdunum option [port]
    --with-logdunum-database <logdunum>                                          set logdunum option [database]
    --with-logdunum-collection <logs>                                            set logdunum option [collection]
    --with-logdunum-failover </your/current/folder/failover.log>                 set logdunum option [failover]

```

Configuration
=============

You can configure logdunum with everything available in ```lib/config.js``` thanks to [cfg](https://github.com/LearnBoost/cfg.js), so you can override settings thank to the process arguments using namespace 'logdunum' or by prefixing environnment variable with 'LOGDUNUM'. It works both with your own program using logdunum and with the ldm CLI :

* examples :

```bash
$> ./myprogram --logdunum-database mylogs
$> ldm --with-logdunum-collection logdunumLogs
$> LOGDUNUM_PORT=27018 ldm -f
```

