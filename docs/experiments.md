# Experiment Log

This document records the experiments, observations, problems and improvements made during the HOI reconstruction project.

## Video Dataset Inspection and Extraction

Status: Completed

- Number of videos: 6
- Original FPS: 30
- Resolution: 640 x 480
- Total extracted frames: 2,316
- Frame format: JPEG
- Naming format: 000000.jpg, 000001.jpg, ...
- All extracted frame counts match the official specifications.

## Experiment 1: Video Preprocessing

**Status:** Completed

### Dataset
- Number of videos: 6
- Original resolution: 640 × 480
- Original frame rate: 30 FPS
- Total original frames: 2,316

### Frame Sampling
- Processing frame rate: 15 FPS
- Sampling strategy: Keep every second frame (indices 0, 2, 4, ...)
- Total processed frames: 1,161

### Metadata
For each processed frame, we saved:
- Processed frame filename
- Original frame index
- Original video timestamp
- Original FPS
- Processing FPS

### Validation
- All six videos were successfully processed.
- Processed frame counts matched expectations.
- Original 30 FPS frames were preserved separately.
- Frame-to-timestamp correspondence was recorded in CSV files.

## Experiment 2: SAM3 Segmentation

**Status:** Not started

Objective:
- Generate hand and object masks.

Observations:
- To be updated.

## Experiment 3: Depth Estimation

**Status:** Not started

Model:
- MoGe-3

Objective:
- Estimate metric-scale depth and camera intrinsics.

Observations:
- To be updated.

## Experiment 4: Hand Reconstruction

**Status:** Not started

Model:
- HaPTIC

Objective:
- Estimate MANO hand trajectories.

Observations:
- To be updated.

## Experiment 5: Object Reconstruction

**Status:** Not started

Model:
- SAM 3D

Objective:
- Generate the 3D object model.

Observations:
- To be updated.

## Experiment 6: Object Pose Estimation

**Status:** Not started

Model:
- FoundationPose

Objective:
- Estimate object 6D pose trajectories.

Observations:
- To be updated.

## Experiment 7: Post-Optimization

**Status:** Not started

Objectives:
- Improve visual similarity.
- Reduce hand-object penetration.
- Improve temporal consistency.

Observations:
- To be updated.

## General Notes

Record:
- Experiment date.
- Video tested.
- Model configuration.
- Errors encountered.
- Results and observations.
- Improvements made.
