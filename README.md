# Hand-Object Interaction Reconstruction

## Introduction

This project focuses on reconstructing 3D Hand-Object Interaction (HOI) from monocular RGB videos.

The goal is to estimate the 3D hand trajectory, reconstruct the 3D object model, and estimate the object's 6D pose trajectory over time.

The project is part of the Introduction to Computer Vision final project at Korea University.

## Project Objectives

1. Initialize MANO hand and object trajectories using feedforward reconstruction models.
2. Estimate metric-scale 3D trajectories in the camera coordinate system.
3. Design a post-optimization strategy to improve reconstruction quality.
4. Reduce hand-object penetration and temporal inconsistencies.
5. Generate the required JSON, GLB, front-view and side-view outputs.

## Pipeline

### 1. Video Preprocessing
- Extract frames from input videos.
- Subsample videos from 30 FPS to 15 FPS.
- Crop hand and object regions to reduce VRAM usage.
- Preserve original frame coordinates.

### 2. Hand Reconstruction
- Use HaPTIC to estimate MANO hand trajectories.

### 3. Object Reconstruction
- Use SAM3 for hand/object segmentation.
- Use MoGe-3 for depth estimation and camera intrinsics.
- Use SAM 3D to reconstruct object geometry.
- Use FoundationPose to estimate object 6D poses.

### 4. Post-Optimization
- Improve visual similarity.
- Reduce hand-object penetration.
- Improve temporal consistency.

### 5. Output Generation
- Interpolate reconstructed trajectories to 30 FPS.
- Export JSON and GLB files.
- Generate front-view and side-view rendering videos.

## Models and Technologies

| Component | Model / Technology |
|---|---|
| Hand reconstruction | HaPTIC |
| Hand/object segmentation | SAM3 |
| Depth and camera intrinsics | MoGe-3 |
| Object reconstruction | SAM 3D |
| Object pose estimation | FoundationPose |
| Optimization | Custom implementation |
| Environment | Python / Google Colab |

## Project Structure

- `notebooks/`: Development and experiments.
- `src/`: Main implementation.
- `configs/`: Shared configurations and hyperparameters.
- `outputs/`: Generated reconstruction results.
- `reports/`: Final project report.
- `docs/`: Experiment logs and documentation.

## Dataset

Six mandatory monocular RGB videos are provided across three difficulty levels: Easy, Normal, and Hard.

Two additional in-the-wild videos are optional and are not used for grading.

## Evaluation

The reconstruction is evaluated using:

1. Hand trajectory reconstruction error.
2. Object trajectory reconstruction error.
3. Hand-object penetration.

The evaluation measures the success rate across video frames.

## Deliverables

- Final JSON outputs.
- Final GLB outputs.
- Source code.
- Two-page PDF report.
- Six front-view rendering videos.
- Six side-view rendering videos.

## Project Timeline

| Period | Milestone |
|---|---|
| Nov 11–13 | Setup and preparation |
| Nov 14–17 | Input preprocessing |
| Nov 18–23 | Hand and object reconstruction |
| Nov 24–28 | Post-optimization |
| Nov 29–Dec 2 | Evaluation and full pipeline |
| Dec 3–5 | Rendering and report |
| Dec 6–7 | Final verification and submission |

## Status

Work in progress.

## References

- [HaPTIC](https://judyye.github.io/haptic-www/)
- [SAM 3](https://github.com/facebookresearch/sam3)
- [SAM 3D Objects](https://github.com/facebookresearch/sam-3d-objects)
- [FoundationPose](https://nvlabs.github.io/FoundationPose/)
- [MoGe-3](https://qft-333.github.io/moge3page/)
