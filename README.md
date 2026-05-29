# Fifth_Step_RoboRacer-SLAM-and-Particle-Filter

# 1. RoboRacer SLAM

**1. Installing slam_toolbox**

```bash
sudo apt install ros-foxy-slam-toolbox
```

**2. Running SLAM**

Inside ``sim_ws`` Launch slam_toolbox

```bash
ros2 launch slam_toolbox online_async_launch.py params_file:=/home/nvidia/f1tenth_ws/src/f1tenth_system/f1tenth_stack/config/f1tenth_online_async.yaml
```

# 2. RoboRacer Particle Filter

**1. Installing range_libc**

- Clone the repo:

```bash
cd
git clone https://github.com/Mohamed-Elgouhary/range_libc.git
```

```bash
cd range_libc/pywrapper
sudo WITH_CUDA=ON python setup.py install
```

**2. Installing particle filter**

```bash
cd $home/sim_ws/src
git clone https://github.com/Mohamed-Elgouhary/particle_filter.git
```

```bash
rosdep install -r --from-paths src --ignore-src --rosdistro foxy -y
```

```bash
colcon build
```

**3. Running Particle Filter**

Inside ``sim_ws``

```bash
ros2 launch particle_filter localize_launch.py
```
