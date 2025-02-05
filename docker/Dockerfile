# Base Image: Start with the official ROS Noetic image for a solid foundation
FROM ros:noetic-ros-base

# Environment Variables (optional): Customize your environment
ENV ROS_WS /catkin_ws

# Install System Dependencies: Add any additional packages your project needs
RUN apt-get update && apt-get install -y \
    python3-catkin-tools \   # Catkin build system for Python 3
    ros-noetic-cv-bridge \   # Image conversion tools (if using cameras)
    <your-other-packages> && \
    rm -rf /var/lib/apt/lists/*  # Clean up to reduce image size

# Create Catkin Workspace: Set up the workspace structure
RUN mkdir -p $ROS_WS/src

# Set Working Directory: Point to the workspace source directory
WORKDIR $ROS_WS/src

# Copy Package Source (optional): If you have custom ROS packages
# COPY ./your_package_src/ .

# Build Catkin Workspace (optional): Only if you copied package source
# RUN /bin/bash -c "source /opt/ros/noetic/setup.bash && catkin build"

# Source ROS Environment: Ensure ROS commands are available
RUN echo "source $ROS_WS/devel/setup.bash" >> ~/.bashrc

# Entrypoint (optional): Launch a ROS node or script on container start
# CMD ["roslaunch", "your_package", "your_launch_file.launch"]
