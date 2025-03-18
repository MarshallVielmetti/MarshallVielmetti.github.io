---
layout: post
title:  "Streamlined Terminal Setup for ROS2"
date:   2025-02-21 13:30:00 -0600
categories: ros2 terminal
---

Building and running ros projects is a pain, especially when you're starting out. Sourcing the 'overlay' and 'underlay' every time you want to run a node or copying a compile_commands over to get `clangd` to work, the process feels clunky. Jumping between different terminal windows is also a pain, especially if working over a remote connection. 

{% highlight zsh %}
source /opt/ros/jazzy/setup.zsh
source install/setup.zsh
colcon build --packages-select <package_name> --symlink-install --cmake-args --DCMAKE_EXPORT_COMPILE_COMMANDS=true
ln -s install/<package_name>/compile_commands.json src/<package_name>/compile_commands.json
{% endhighlight zsh %}

## TMUX
Tmux is a 'terminal multiplexer'. Basically, it lets you have many terminals easily accessible, running inside one terminal.  And, if you close the terminal window by mistake, you can jump right back in without restarting your nodes. 


