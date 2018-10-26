## The `sbatch` command

The sbatch command submits batch jobs into the Slurm batch queue.
Batch jobs are those that run on the compute nodes in the
background. An analogous command is the
[sinteractive](interactive-jobs.html) command, except that
this allows you to run a job on the compute nodes while interacting
directly. Many of the flags used in the `sbatch` command can be used
in `sinteractive`.

The `sbatch` command is most powerful when using appropriate flags to
specify exactly how you would like your job to run. The first, less
common way is to add the flags in the terminal window after sbatch:

```bash
sbatch --flag1 --flag2
```

The second is to create a script that includes the bash flags, and to
submit that script. See the [Job Submission](submission.html)
page for information on this, or view one of our recommended
[templates](https://raw.githubusercontent.com/ResearchComputing/Documentation/master/Templates/General-Job-Template.sh)
for an example of how to best write up a script.

The primary reason that writing a script is more ideal than putting
the flags behind the `sbatch` command in the terminal window is that
when you put these flags in a script you can reuse the script in the
future. It's also less typing, and we all like that!

To submit a job using a script, we will type:

``` bash
sbatch test.sh
```

Where `test.sh` is our sample bash script. Note - you do not need to
only write bash scripts for this to work.

Below, let's look at some common `sbatch` flags.

### Important flags

The `sbatch` command supports many optional flags. To review all the
options, please visit the Slurm [sbatch
page](http://slurm.schedmd.com/sbatch.html). Below, we have listed a
few ones you may want to consider when submitting your job via
`sbatch`.

|        Type         |                    Description                    |           Flag             |
|---------------------|---------------------------------------------------|----------------------------|
|     Allocations     |Specify an allocation account if you have multiple |    --account=account_no    |
|     Partitions      |              Specify a partition                  |--partition=partition_name  |
|    Sending emails   |Receive email at beginning or end of job completion|      --mail-type=type      |
|    Email address    |         Email address to receive the email        |      --mail-user=user      |
|   Number of nodes   |     The number of nodes needed to run the job     |       --nodes=nodes        |
|   Number of tasks   |     The number of cores needed to run the job     |     --ntasks=processes     |
|  Quality of service |              Specify a QOS                        |          --qos=qos         |
|      Wall time      |   The max. amount of time your job will run for   |      --time=wall time      |
|       Job Name      |     Name your job so you can identify in queue    |	--job-name=jobname         |