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
