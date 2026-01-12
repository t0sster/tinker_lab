# Isaac Lab environment for Tinker project


## Installation

- install [IsaacSim](https://docs.isaacsim.omniverse.nvidia.com/5.1.0/installation/index.html) 
        and [IsaacLab](https://isaac-sim.github.io/IsaacLab/main/source/setup/installation/index.html) 
        according developers' manual
    - to solve **omni** package error *run* `./isaaclab.sh -i` in **IsaacLab/** directory 

- install [bipedal_locomotion](https://github.com/t0sster/bipedal_locomotion_isaaclab.git) - my fork for Tinker
    - to solve **toml** package error use `pip install -e exts/bipedal_locomotion --no-build-isolation`
    - to solve the problem with **torch** version change 18'th row in */ext/bipedal_locomotion* to `"torch>=2.4.0"`
            or **just use torch==2.4.0** - it's clear!
    - after the installation make sure that you use *bipedal_locomotion* project that was previously adapted
            for a new versions of IsaacSim and all `omni.isaac.lab...` python imports is being changed to `isaaclab...`, etc.

## Launch

```bash
python scripts/rsl_rl/train.py --task=Isaac-PF-Blind-Flat-v0 --num_envs=8
```

```bash
python scripts/rsl_rl/train.py --task=Isaac-PF-Blind-Flat-v0 --num_envs=64 --max_iterations=100
```