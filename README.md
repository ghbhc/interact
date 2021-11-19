# interact
Easily start an interactive job on a Slurm HPC cluster

This is essentially a wrapper script for `srun`, calling a login shell of /bin/bash (or whatever shell you specify), with default resources, or specified resources.  The impetus for this script was the desire for a way for users to easily and dynamically specify resources needed for interactive jobs.  To adjust default values, just change the values listed at the top of the script.  For clarity's sake, the script will echo out the srun command that is being ran.

## How to Use

```
interact [OPTIONS]
```

### Examples

To start a job using the default values, but with 4 cores:

```
interact --cpus-per-task 4
```

To start an interactive job with the default values, but with 100gb of memory, using /bin/zsh, and a job name of "test-job"

```
interact --mem 100gb --shell /bin/zsh --job-name test-job
```

### Help Output

```
$ interact -h

Usage: interact [OPTIONS]

Description: Start an interactive job

    -c, --cpus-per-task         CPU cores per task (default: 1)
    -J, --job-name              Job name (default: interact)
    -n, --ntasks                Number of tasks (default: 1)
    -N, --nodes             	Number of nodes (default: 1)
    -p, --partition             Partition for interactive job (default: inter_p)
    -q, --qos               	Request a quality of service for the job.
    -t, --time              	Maximum run time for interactive job (default: 12:00:00)
    -w, --nodelist              List of node name(s) on which your job should run
    --constraint                Job constraints
    --gres                  	Generic consumable resources
    --mem                  	Memory per node (default 2GB)
    --shell                 	Absolute path to the shell to be used in your interactive job (default: /bin/bash)
    --wckey                 	Wckey to be used with job
    --x11                   	Start an interactive job with X Forwarding
    -h, --help              	Display this help output
```
