# Wishbone configuration

## Quick start on Anemone (NOC Supercomputing Service)
```shell
git clone git@github.com:NOC-MSM/Wishbone.git -b main
cd Wishbone
./setup -s Anemone
```
The setup script downloads nemo, compiles tools and configurations.

To run NEMO:
```shell
cd nemo/cfgs/GLOBAL_QCO/eORCA025
```

There are a few variables to set in `run_nemo1326_24x_v2.slurm`. For example, the following variables will generate a 2-hour simulation split in 1-hour jobs.
```bash
# ========================================================
# PARAMETERS TO SET
# Restart frequency (<0 days, >0 hours)
FREQRST=1
# Simulation length (<0 days, >0 hours)
LENGTH=2
# Parent initial time step (0: infer from time.step)
# PARENT_IT000 != 0 -> auto-resubmission is switched OFF
PARENT_IT000=0
# Name of this script (to resubmit)
SCRIPTNAME=run_nemo1326_24x_v2.slurm
# =======================================================
```
Finally:
```shell
sbatch run_nemo1326_24x_v2.slurm
```




## Setup
### Global eORCA025
Resolution:
- Horizontal: 1/4°
- Vertical: 75 levels
