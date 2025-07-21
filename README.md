# Neural Networks for Optimal Control (NNs-for-OC)

## Overview

This project explores the application of modern neural network architectures, particularly State-Space Models (SSMs) like the Linear Recurrent Unit (LRU), for solving optimal control problems. It provides a framework for defining control systems (plants), implementing neural network-based controllers, and running training and evaluation experiments. The primary examples focus on robotic navigation tasks, including single and multi-obstacle avoidance.

## Project Structure

The repository is organized into several key directories, each with a specific purpose:

*   **`controllers/`**: Contains the implementations of the neural network controllers.
    *   `PB_controller.py`: Implements the `PerfBoostController`, the main controller used in the experiments.
    *   `m_operators/`: Holds the core building blocks for the controllers, such as the SSM implementation (`ssm.py`), non-linear activation functions (`non_linearities.py`), and other utilities.

*   **`plants/`**: Defines the dynamics of the physical systems to be controlled.
    *   `robots/`: Contains the system dynamics for the robot models.
    *   `tanks/`: Contains the system dynamics for a tank model.

*   **`experiments/`**: This is the main directory for running simulations. Each subdirectory corresponds to a specific control problem.
    *   `robot_single_obstacle/`: Scripts for training and evaluating a robot navigating around a single obstacle. Includes training, evaluation, and plotting scripts.
    *   `robot_multi_obstacle/`: Scripts for the more complex task of navigating a slalom course with multiple obstacles.
    *   `tank/`: Scripts related to a tank control problem.
    *   Each experiment folder typically contains:
        *   A main training script (e.g., `Multi_obstacle_sol2.py`).
        *   Dataset definitions (e.g., `multi_obstacle_dataset.py`).
        *   System definitions (e.g., `robots_sys.py`).
        *   Custom loss functions (e.g., `loss_functions.py`).
        *   Plotting functions for visualization.
        *   A `saved_results/` directory to store logs, model weights, and plots from training runs.

*   **`assistive_functions.py`**: A collection of helper functions used across the project.

*   **`requirements.txt`**: A list of all Python dependencies required to run the project.

## Getting Started

### Prerequisites

Ensure you have Python 3.8+ installed.

### Installation

1.  Clone the repository to your local machine.
2.  Install the required dependencies using pip:
    ```bash
    pip install -r requirements.txt
    ```

### Running an Experiment

You can run any experiment by executing its main training script. For example, to start the multi-obstacle robot training:

```bash
python experiments/robot_multi_obstacle/Multi_obstacle_sol2.py