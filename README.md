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

## Launch training

```bash
python scripts/rsl_rl/train_TK.py --task=Isaac-TK-Blind-Flat-v0 --num_envs=8
```

```bash
python scripts/rsl_rl/train_TK.py --task=Isaac-TK-Blind-Flat-v0 --num_envs=2048 --max_iterations=20000
```

```bash
python scripts/rsl_rl/train_TK.py --task=Isaac-TK-Blind-Flat-v0 --num_envs=512 --max_iterations=30000 --checkpoint_path=/logs/rsl_rl/tk_blind_flat/
```

## Play trained policy

```bash
python scripts/rsl_rl/play_TK.py --task=Isaac-TK-Blind-Flat-Play-v0 --num_envs=1 --checkpoint_path=path/to/checkpoint
```

example path:
```bash
/logs/rsl_rl/tk_blind_flat/2026-02-23_01-53-56/model_19000.pt
```