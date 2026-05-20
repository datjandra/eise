# EISE - Easy Image Search Engine

A modern, browser-based image matching and visual search application powered by computer vision techniques. EISE compares a query image against a dataset and ranks results based on feature-level similarity using FAST keypoint detection and BRIEF descriptors.

**Live Demo:** https://datjandra.github.io/eise/

---

## Overview

EISE demonstrates real-time, client-side image retrieval using classical computer vision methods. Instead of relying on text tags or metadata, the system analyzes visual structure directly and returns ranked matches based on feature correspondence.

The updated interface focuses on a **clean search-and-explore workflow**:

- A **query panel** for selecting input images
- A **results grid** showing ranked matches
- A **modal-based detail viewer** for deep inspection of feature matches

---

## New User Interface & Experience

The application has been redesigned for clarity and usability:

### 🔍 Query Panel (Left Sidebar)
- Select a query image from a dropdown menu
- Preview the selected image instantly
- Run matching with a single button click
- Live status indicator shows processing state and best score

### 🧩 Results Grid (Main Area)
- Ranked visual similarity results displayed as cards
- Each result shows:
  - Thumbnail preview
  - Similarity score
  - Rank position
- Hover interaction highlights candidate images
- Click any result to inspect detailed matches

### 🔬 Match Detail View (Modal)
- Full-screen overlay visualization
- Side-by-side comparison of query vs matched image
- Colored feature correspondences:
  - Keypoints
  - Match lines between descriptors
- Focused inspection without cluttering the main UI

This replaces the previous canvas-based side panel approach with a **more modern, modal-driven experience optimized for exploration**.

---

## How It Works

EISE uses classical feature-based image matching:

### 1. Feature Detection (FAST)
The FAST algorithm identifies corner points in images that represent visually distinctive regions.

### 2. Feature Description (BRIEF)
Each keypoint is encoded using BRIEF descriptors, producing compact binary feature vectors.

### 3. Feature Matching
Descriptors from the query image are compared against all dataset images to find correspondences.

### 4. Similarity Scoring
Each candidate image receives a score based on the average confidence of matched features.

### 5. Ranking & Visualization
Results are sorted by similarity score and visualized in a responsive grid. Detailed matches can be inspected via the modal viewer.

---

## Features

- ⚡ Real-time image matching directly in the browser
- 🧠 Feature-based similarity using FAST + BRIEF
- 🖼️ Ranked results grid with visual previews
- 🔬 Interactive match inspection via modal viewer
- 🎯 Clean separation of search and exploration workflow
- 🔒 Fully client-side processing (no backend required)
- 📱 Responsive UI built with Bootstrap

---

## Technology Stack

- **Tracking.js**
  - FAST corner detection
  - BRIEF feature descriptors
  - Descriptor matching utilities

- **Bootstrap 3.3.5**
  - Responsive layout system
  - UI components (grid, modal, buttons)

- **jQuery 2.1.4**
  - DOM manipulation
  - Event handling

- **HTML5 Canvas**
  - Feature visualization
  - Side-by-side image rendering
  - Match line drawing

---

## Project Structure
eise/
├── index.html
├── images/
│ ├── img_1.jpg
│ ├── img_2.jpg
│ ├── img_3.jpg
│ ├── img_4.jpg
│ └── img_5.jpg
├── tracking.js/
├── bootstrap-3.3.5-dist/
├── jquery-2.1.4/
└── README.md

---

## How to Use

1. **Select a Query Image**
   - Choose an image from the dropdown in the query panel

2. **Run Matching**
   - Click “Run Matching” to compute similarity scores across the dataset

3. **Explore Results**
   - View ranked results in the grid
   - Each card shows similarity score and preview

4. **Inspect Matches**
   - Click any result to open detailed feature matching view
   - Analyze keypoint correspondences between images

---

## Algorithm Details

### FAST Corner Detection
Detects high-contrast keypoints that are stable under transformations.

### BRIEF Descriptors
Encodes local pixel comparisons around keypoints into compact binary vectors.

### Matching Strategy
- Descriptor matching between query and dataset images
- Confidence scoring based on match quality
- Averaging used to compute final similarity score per image

---

## Parameters

- **Descriptor Length (`descriptorLength`)**  
  Controls BRIEF descriptor size (default: 256 bits)

- **Match Visualization Limit (`slice(0, 25)`)**  
  Limits displayed matches for clarity in UI

---

## Use Cases

- Visual similarity search
- Reverse image lookup prototypes
- Computer vision education and demos
- Feature matching experimentation
- Interactive ML/CV UI prototypes

---

## Browser Compatibility

Requires a modern browser supporting:

- HTML5 Canvas
- ES5+ JavaScript
- DOM image processing APIs

---

## Development Context

EISE was originally built for a hackathon and has been refactored into a more modern UI architecture emphasizing:

- Separation of search and visualization
- Cleaner interaction model
- Scalable result presentation
- Improved usability for exploration tasks

---

## Performance Notes

- Entire pipeline runs client-side
- Performance depends on:
  - Image resolution
  - Number of dataset images
  - CPU performance for feature extraction
- No server round-trips required

---

## Future Enhancements

- Upload custom query images
- Larger-scale dataset indexing
- WebGL-accelerated feature extraction
- Better descriptor matching (e.g., FLANN-style optimization)
- Mobile-first UI redesign
- Clustering-based result grouping

---

## License

Project created for the LevelUp 1 hackathon. See repository for license details.

---

## Author

Created by [datjandra](https://github.com/datjandra)

---

For more information on Tracking.js: https://trackingjs.com/
