# EISE - Easy Image Search Engine

A simple yet powerful JavaScript-based image search engine that uses computer vision techniques to find and match similar images. Built with [Tracking.js](https://trackingjs.com/) for the LevelUp 1 hackathon.

**[Live Demo](https://datjandra.github.io/eise/)**

## Overview

EISE is an innovative web application that demonstrates advanced image matching capabilities using client-side computer vision. Rather than relying on text-based search or metadata, EISE analyzes the visual content of images to find the best matches based on their visual similarities and distinctive features.

## How It Works

EISE employs sophisticated image processing and feature detection algorithms to identify and match images:

1. **Feature Detection**: The application uses the FAST (Features from Accelerated Segment Test) corner detection algorithm to identify distinctive feature points in images.

2. **Feature Descriptor Generation**: Once corner points are identified, the system generates BRIEF (Binary Robust Independent Elementary Features) descriptors for each corner, creating a compact binary fingerprint of the image's visual characteristics.

3. **Image Matching**: The engine compares the query image against a database of images by matching their descriptors. It calculates confidence scores based on the quality and number of matching feature points.

4. **Similarity Scoring**: Images are ranked by their average confidence scores, with the best match (highest average confidence) displayed as the top result along with visual indicators showing the matched feature points.

5. **Visual Feedback**: The results are displayed with colored lines and points connecting the matched features between the query image and the best match, providing transparency into how the matching algorithm works.

## Features

- **Real-Time Image Matching**: Instantly compare a query image against a database of images
- **Visual Feature Matching**: See exactly which features matched between images with colored overlays
- **Interactive Query Selection**: Choose from multiple query images (Maelstrom, Smiley, Elon) to search against the database
- **Responsive Interface**: Built with Bootstrap 3.3.5 for a clean, responsive user experience
- **Client-Side Processing**: All image processing happens in the browser using Tracking.js, ensuring fast performance and privacy

## Technology Stack

- **Tracking.js**: JavaScript library for computer vision and image processing
  - FAST corner detection algorithm
  - BRIEF feature descriptor generation
  - Image matching and correlation
- **Bootstrap 3.3.5**: Frontend framework for responsive UI design
- **jQuery 2.1.4**: DOM manipulation and utility functions
- **HTML5 Canvas**: For rendering images and visualization of matched features
- **Google App Engine**: Cloud hosting platform

## Project Structure

```
eise/
├── index.html
├── images/
├── tracking.js/
├── bootstrap-3.3.5-dist/
├── jquery-2.1.4/
└── README.md
```

## How to Use

1. **Select a Query Image**: Use the dropdown menu to choose a query image (Maelstrom, Smiley, or Elon)
2. **View Results**: The canvas displays a side-by-side comparison of the query image and the best matching image from the database
3. **Analyze Matches**: Colored lines and points on the canvas show the matched features, helping you understand how the algorithm identified similar images

## Algorithm Details

### FAST Corner Detection
The FAST algorithm identifies corner points in images by examining the intensity of pixels in a circular neighborhood. These corner points represent distinctive features that are likely to be found in other similar images.

### BRIEF Descriptors
BRIEF generates a compact binary descriptor for each corner point by comparing pixel intensities at specific locations around that corner. This creates a fingerprint that can be rapidly compared with other descriptors.

### Matching Confidence
The matching algorithm computes matches between descriptors of the query image and each database image. For each image, the system calculates an average confidence score based on all matched points. Higher scores indicate greater visual similarity.

## Parameters

The application includes tunable parameters that affect matching behavior:

- **Descriptor Length (`descriptorLength`)**: Set to 256 bits, controlling the precision of feature descriptors
- **Matches Shown (`matchesShown`)**: Limited to 30 matches for visualization clarity, though the algorithm may find more

## Use Cases

- **Product Discovery**: Find similar items in an image database
- **Content Recommendation**: Suggest visually similar images
- **Reverse Image Search**: Locate images with similar visual characteristics
- **Computer Vision Learning**: Understand how feature detection and matching work

## Browser Compatibility

EISE requires a modern web browser with support for:
- HTML5 Canvas API
- JavaScript ES5+
- WebGL (optional, for accelerated processing)

## Development Context

This project was developed for the LevelUp 1 hackathon, showcasing practical applications of computer vision techniques in web development. It demonstrates how sophisticated image processing can be accomplished entirely on the client-side using JavaScript libraries.

## Performance Notes

- Image matching is performed in the browser, making the application responsive and independent of backend server performance
- Processing time scales with image size and the number of images in the database
- The FAST and BRIEF algorithms are optimized for real-time performance on standard hardware

## Future Enhancements

Potential improvements to the system could include:
- Larger image databases for more comprehensive search results
- Support for custom image uploads
- Fine-tuned algorithm parameters for domain-specific matching
- Mobile optimization
- Performance benchmarking and optimization

## License

This project was created for the LevelUp 1 hackathon. Please refer to the repository for specific licensing information.

## Author

Created by [datjandra](https://github.com/datjandra)

---

For more information about Tracking.js, visit: https://trackingjs.com/
