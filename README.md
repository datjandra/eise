# EISE - Easy Image Search Engine

A browser-based image matching and visual search system that uses computer vision techniques to compare a query image against a dataset and return ranked results based on visual similarity.

**Live Demo:** https://datjandra.github.io/eise/

---

## Overview

EISE is a client-side image search application that performs feature-based matching directly in the browser. Instead of relying on metadata or text labels, it analyzes visual structure to identify similar images.

The interface is designed around a simple workflow:

- Select a query image
- Run matching against a dataset
- Explore ranked results
- Inspect detailed feature correspondences

---

## User Interface & Experience

### 🔍 Query Panel (Left Sidebar)
The query panel is the entry point for image search:

- Dropdown selection of available query images
- Instant preview of the selected query image
- “Run Matching” button to execute the search
- Live status indicator showing processing state and best match score

---

### 🧩 Results Grid (Main Area)
The results section displays ranked matches in a responsive grid layout:

- Visual thumbnails of matched images
- Rank ordering based on similarity score
- Confidence score for each result
- Hover interaction for visual emphasis
- Clickable cards to inspect individual matches

---

### 🔬 Match Detail Viewer (Modal)
Detailed inspection is presented in a modal overlay:

- Side-by-side visualization of query and matched image
- Keypoint correspondences drawn between images
- Color-coded feature match visualization
- Focused, distraction-free inspection mode

---

## How It Works

EISE uses classical feature-based computer vision techniques:

### 1. Feature Detection (FAST)
Corner points are detected in both query and dataset images using the FAST algorithm, identifying visually distinctive regions.

### 2. Feature Description (BRIEF)
Each keypoint is encoded using BRIEF descriptors, producing compact binary representations of local image structure.

### 3. Feature Matching
Descriptors from the query image are compared against each dataset image to identify matching keypoints.

### 4. Similarity Scoring
A similarity score is computed for each image based on the average confidence of matched feature pairs.

### 5. Ranking & Visualization
Results are sorted by similarity score and presented in a ranked grid. Selected results can be explored in detail through feature visualization.

---

## Features

- ⚡ Fully client-side image matching
- 🧠 Feature-based similarity using FAST + BRIEF
- 🖼️ Ranked visual results grid
- 🔬 Interactive match visualization in modal view
- 🎯 Clean separation between search and exploration
- 🔒 No backend required — runs entirely in the browser
- 📱 Responsive layout using Bootstrap

---

## Technology Stack

- **Tracking.js**
  - FAST corner detection
  - BRIEF feature descriptors
  - Descriptor matching utilities

- **Bootstrap 3.3.5**
  - Responsive grid system
  - UI components (buttons, modal, layout)

- **jQuery 2.1.4**
  - DOM manipulation
  - Event handling

- **HTML5 Canvas**
  - Image rendering
  - Feature visualization
  - Match line drawing

---

## Project Structure
```
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
```

---

## How to Use

1. Select a query image from the dropdown menu
2. Click “Run Matching” to search the dataset
3. View ranked results in the results grid
4. Click any result to open detailed match visualization

---

## Algorithm Details

### FAST Corner Detection
FAST identifies high-contrast corner points that are stable and repeatable across images.

### BRIEF Descriptors
BRIEF encodes local pixel intensity comparisons around keypoints into compact binary descriptors.

### Matching Strategy
- Descriptor matching between query and dataset images
- Confidence-based scoring of matched pairs
- Averaging of match confidence to compute final similarity score

---

## Parameters

- **Descriptor Length (`descriptorLength`)**
  - Controls BRIEF descriptor size (default: 256 bits)

- **Match Visualization Limit**
  - Only top matches are displayed for clarity in visualization (e.g., 25–30 matches)

---

## Use Cases

- Visual similarity search
- Reverse image lookup prototypes
- Computer vision education and demonstrations
- Feature matching experimentation
- UI prototyping for image retrieval systems

---

## Browser Compatibility

EISE works in modern browsers supporting:

- HTML5 Canvas API
- ES5+ JavaScript features
- Standard DOM APIs

---

## Performance Notes

- All computation runs entirely in the browser
- Performance depends on:
  - Image resolution
  - Number of dataset images
  - CPU performance for feature extraction
- No server communication required

---

## Future Enhancements

- Support for user-uploaded query images
- Larger dataset indexing and optimization
- Improved matching algorithms (e.g., FLANN-style search)
- WebGL acceleration for feature extraction
- Mobile-first interface improvements
- Clustering-based result grouping

---

## License

This project was created for the LevelUp 1 hackathon. Refer to the repository for licensing details.

---

## Author

Created by [datjandra](https://github.com/datjandra)

---

For more information on Tracking.js, visit: https://trackingjs.com/
