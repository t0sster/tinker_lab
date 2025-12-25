# Isaac Lab environment for Tinker project


## Installation

- install isaacSim and isaacLab according developers' manual
    - to solve **omni** package error run at IsaacLab/ directory `./isaaclab.sh -i`
- install bipedal_locomotion
    - to solve **toml** package error use `pip install -e exts/bipedal_locomotion --no-build-isolation`
    - to solve the problem with **torch** version change 18'th row in */ext/bipedal_locomotion* to `"torch>=2.4.0"`
    or **just use torch==2.4.0** - it's clear!
    - after the installation make sure that you use *bipedal_locomotion* project that was previously adapted
    for a new versions of IsaacSim and all `omni.isaac.lab...` is being changed to `isaaclab...`, etc.

## Launch

- python scripts/rsl_rl/train.py --task=Isaac-PF-Blind-Flat-v0 --num_envs=8
- python scripts/rsl_rl/train.py --task=Isaac-PF-Blind-Flat-v0 --num_envs=64 --max_iterations=100