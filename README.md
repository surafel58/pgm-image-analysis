# Environmental Mapping with Undirected Graphical Models

This project implements a solution for mapping environmental features (forests, grassy areas) using satellite imagery and Markov Random Fields (MRFs), which are undirected graphical models.

## Project Overview

The project performs the following tasks:

1. **Satellite Image Retrieval**: Fetches satellite imagery using Google Maps API
2. **Elevation Data Retrieval**: Gets elevation information using Google Elevation API
3. **Image Segmentation**: Uses Markov Random Fields (MRF) to segment the image into different environmental features
4. **Environmental Feature Mapping**: Identifies and visualizes the environmental features with distance measurements

## Implementation

The solution is implemented in a Jupyter notebook (`environmental_mapping_solution.ipynb`) using Python with the following libraries:
- `requests` and `Pillow` for image retrieval
- `numpy` and `matplotlib` for data handling and visualization
- `pygco` for graph-cut optimization in MRF inference
- `scipy.ndimage` for connected component labeling

## Markov Random Field Approach

The key part of this implementation is the use of Markov Random Fields for image segmentation:

1. **Unary Potentials**: Based on pixel color characteristics, calculating the cost of assigning each label to each pixel
2. **Pairwise Potentials**: Encouraging spatial smoothness by penalizing label differences between neighboring pixels
3. **Graph-Cut Optimization**: Finding the optimal labeling that minimizes the total energy

This approach produces more coherent segmentation than simple clustering methods by considering both color information and spatial relationships.

## Running the Code

To run this project:

1. Make sure you have the required libraries installed:
   ```
   pip install requests pillow numpy matplotlib scikit-learn pygco
   ```

2. Add your Google Maps API key to the notebook where indicated

3. Run the Jupyter notebook `environmental_mapping_solution.ipynb`

## Output

The notebook generates several output files:
- `satellite_image.png`: The retrieved satellite image
- `segmentation_results.png`: Visualization of the MRF segmentation
- `environmental_mapping.png`: Final environmental feature map with distance information

## References

This implementation draws from concepts in:
- Probabilistic Graphical Models
- Computer Vision and Image Processing
- Environmental Feature Extraction
- Graph-Cut Optimization

## Notes

- The MRF parameters (color models, smoothness penalty) may need to be adjusted for different locations and environmental features.
- The Google Maps API key requires appropriate permissions for Static Maps and Elevation APIs. 
