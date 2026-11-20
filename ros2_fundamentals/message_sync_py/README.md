# message_sync_py

Python example for synchronizing messages from multiple ROS 2 topics with `message_filters`.

## Build and run

From the repository root, after sourcing ROS 2 Humble:

```bash
colcon build --base-paths ros2_fundamentals --packages-up-to message_sync_py --symlink-install
source install/setup.bash
```

Start the publisher and subscriber in separate terminals (source `install/setup.bash` in each):

```bash
ros2 run message_sync_py multi_publisher
ros2 run message_sync_py sync_subscriber
```

The Python subscriber registers a callback for synchronized messages from `/camera_data` and `/lidar_data` using the approximate-time policy. See the [C++ example](../message_sync/README.md) for the paired implementation.
