# Enhancing momepy: Adding Support for Street-Based Tessellation (ST)

## Overview 

Momepy is a powerful tool for analyzing urban morphology, already supporting Morphological Tessellation (MT) and Enclosed Tessellation (ET). Adding Street-Based Tessellation (ST) will provide a new intuitive tessellation method, enabling the analysis of city blocks defined by natural barriers such as street networks, rivers, and railways.

## Objectives

1. Extend momepy's functionality by implementing Street-Based Tessellation (ST).
2. Create a method that generates city blocks as polygons based on an input street network and other natural barriers.
3. Ensure seamless integration of ST with existing functionalities, maintaining user-friendliness.

## Implementation Steps

### 1. Data Requirements
- **Input**: 
  - Street network geometry (as GeoDataFrame or similar).
  - Optional: Additional natural barriers (e.g., rivers, railways).
- **Output**: 
  - City blocks represented as polygons in a GeoDataFrame.

### 2. Algorithm Design
1. Parse input street network and additional barriers.
2. Create a planar graph representation of the street network using a library like `networkx` or `osmnx`.
3. Identify intersections and nodes to define block boundaries.
4. Perform graph-based partitioning of space into blocks using intersections and edges.
5. Convert resulting partitions into polygon geometries.

### 3. Integration with momepy
- Add a new class or function, e.g., `momepy.StreetBasedTessellation`.
- Include parameters for customization (e.g., buffer size for barriers).
- Ensure compatibility with existing tessellation methods for comparative analysis.

### 4. Implementation Details
- Use `shapely` for geometric operations and polygon creation.
- Leverage `geopandas` for managing spatial data efficiently.
- Utilize existing momepy utilities wherever possible to avoid redundant code.

### 5. Example Usage
```python
import momepy
import geopandas as gpd

# Load street network as GeoDataFrame
streets = gpd.read_file("street_network.geojson")

# Create Street-Based Tessellation
blocks = momepy.StreetBasedTessellation(streets)

# Visualize or analyze the resulting blocks
blocks.plot()
