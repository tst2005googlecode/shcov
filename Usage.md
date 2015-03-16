This page contains some short usage instructions for **shcov** and **shlcov**. Invoke the programs  with `--help` or read the man-pages for additional options.

### Generating data ###

shcov will output data in `/tmp/shcov`, so if you are happy with this,
just run your script with shcov first:

```
shcov your-script.sh args...
```

If you run your script multiple times, shcov will just update the
data. It also detects when the script source has been modified and
then start counting from zero.

### Generating HTML output of the data ###
The shlcov tool generates HTML output of the data shcov collected. It
is invoked with the data directory and an output directory as
argument:

```
shlcov /tmp/shcov html
```

this will generate output in the html directory in your working
dir. Now point your browser to html/index.html and look through the
collected data.

### Using shcov via hash-bang ###
You can also start shcov via a "hash bang" instead of bash. This can be useful when running tests on many scripts which can be started from different places. To do this, replace the normal hash bang with

```
#!/usr/bin/env python /path/to/shcov
```

obviously this replacement can be automated with the use of **grep** and **ed** or similar.