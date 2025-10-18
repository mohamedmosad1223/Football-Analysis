# Football Video Analytics — Player & Ball Tracking

## Overview

This project demonstrates an **AI-based football video analysis system** built using `supervision`, `roboflow`, and `Hugging Face` vision models. The system processes match footage to detect, track, and analyze player movement, ball position, and tactical patterns.

It combines computer vision, deep learning, and geometric transformations to provide a detailed view of player behavior and match dynamics.

---

## Core Features

### 🎯 Detection

* Detects **players, referees, goalkeepers, and the ball** in each frame using Roboflow object detection models.
* Models are trained or fine-tuned specifically for football match footage.

### 🔄 Tracking

* Uses **ByteTrack** to maintain player identities across video frames.
* Ensures stable player tracking even when occlusion or overlaps occur.

### 🧩 Team Classification

* Automatically assigns detected players to their respective teams using color-based clustering.
* Goalkeepers are identified based on field position and distance to goal area.

### 🧠 Representation Learning

* Extracts **image embeddings** from cropped player images using `SiglipVisionModel` (Hugging Face).
* Applies **UMAP** for dimensionality reduction and **KMeans** for player clustering.

### 🗺️ Field Projection (Homography)

* Projects player and ball coordinates onto a **2D pitch map** using homography transformation.
* Enables tactical visualization (positions, ball trajectory, Voronoi diagrams, etc.).

### 📊 Visualizations

* Generates annotated video with bounding boxes, IDs, and team labels.
* Produces pitch maps and **Voronoi regions** to show area control.
* Supports trajectory tracing for ball and players.

---

## System Workflow

1. **Video Input**: Load match footage (MP4).
2. **Object Detection**: Detect players, referees, and ball.
3. **Tracking**: Assign persistent IDs via ByteTrack.
4. **Homography Transformation**: Map detections to real-world field coordinates.
5. **Team Classification**: Separate players into teams based on appearance.
6. **Visualization**: Render annotated video and tactical overlays.
7. **Embedding Analysis (optional)**: Cluster player embeddings for behavioral or tactical patterns.

---

## Tools & Technologies

| Category      | Tool / Library              |
| ------------- | --------------------------- |
| Detection     | Roboflow API models         |
| Tracking      | ByteTrack (via supervision) |
| Vision        | supervision, OpenCV         |
| Embeddings    | Hugging Face (Siglip)       |
| Clustering    | UMAP, KMeans                |
| Visualization | Plotly, Matplotlib          |

---

## Example Output

* **Annotated Match Video** showing:

  * Player IDs and bounding boxes.
  * Ball trajectory.
  * Team color classification.
* **Tactical Map View**:

  * Player and ball positions projected on the pitch.
  * Optional Voronoi map for team space control.

---

## Future Enhancements

* Integrate **event detection** (shots, goals, passes).
* Add **heatmaps** for player movement intensity.
* Support for **real-time inference** on live matches.
* Build a dashboard with **interactive pitch analytics**.

---

## Summary

This project provides a **complete workflow for football match understanding** — from raw video to tactical visualization. It’s designed for developers, analysts, and researchers interested in **sports analytics**, **computer vision**, and **AI-assisted tactical analysis**.
